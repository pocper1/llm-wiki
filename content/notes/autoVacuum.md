# PostgreSQL Transaction ID 堆積與 Auto Vacuum 失效問題

## 這是什麼問題？

這是一個 **Transaction ID Wraparound** 威脅 + **Auto Vacuum 被阻塞** 的組合問題。

---

## 核心概念：PostgreSQL 的 MVCC 機制

PostgreSQL 用 **MVCC（Multi-Version Concurrency Control）** 來處理併發：

- 每筆資料的每個版本都有一個 `xmin`（建立它的 transaction ID）
- 當資料被 UPDATE / DELETE，舊版本不會立刻消失，而是變成 **dead tuple**
- **Vacuum** 的工作就是清理這些 dead tuple，回收空間

```
INSERT row → live tuple (xmin=100)
    ↓
UPDATE row → old version 變 dead tuple, 新版本 (xmin=200)
    ↓
VACUUM → 清掉 dead tuple，回收 page 空間
```

---

## 問題鏈解析

### Step 1：你的同步程式有 Long-running Transaction

```
BEGIN;
-- 做一些同步操作...
-- 但 transaction 一直沒有 COMMIT / ROLLBACK
-- 或是異常後沒有正確清理
```

這個 transaction 拿到了一個很早的 **Transaction ID（xid）**，例如 `xid = 500`

### Step 2：Auto Vacuum 被這個 transaction 卡住

Auto Vacuum 清理 dead tuple 的前提是：

> **dead tuple 對所有活躍的 transaction 都不可見，才能被清理**

因為 xid=500 的 transaction 還活著，PostgreSQL 必須保留 **xid=500 之後產生的所有版本**，以確保這個 transaction 能讀到一致的資料。

```
Long transaction: xid=500 (一直沒結束)
                    ↓
Auto Vacuum 看到: "xid=500 還活著，我不能清比 500 新的 dead tuple"
                    ↓
結果: dead tuple 全部積著清不掉
```

### Step 3：dead tuple 大量堆積 → Table Bloat

```
正常 page:  [live][live][live][live]  → 密集、查詢快
Bloat page: [dead][live][dead][live]  → 離散、要 scan 更多 page
```

- Table 實體大小膨脹
- Index 也隨之 bloat
- Sequential scan / Index scan 要讀更多 pages
- Query 變慢 → **Canvas 服務 timeout**

### Step 4：Transaction ID 堆積的額外風險

PostgreSQL 的 xid 是 **32-bit 循環計數器**（約 21 億），如果 long transaction 讓 xid 無法推進，久了會接近 **wraparound**，屆時 PostgreSQL 會強制關閉整個 DB 防止資料損毀。

---

## 為什麼這樣可以解決？

### 砍掉 long transaction

```sql
SELECT pg_terminate_backend(pid)
FROM pg_stat_activity
WHERE state = 'idle in transaction'
  AND query_start < now() - interval '10 minutes';
```

- Long transaction 消失 → **vacuum 的阻塞解除**
- Auto Vacuum 可以重新正常運行

### VACUUM FULL 的作用

| | `VACUUM` (一般) | `VACUUM FULL` |
|---|---|---|
| 清理 dead tuple | ✅ | ✅ |
| 回收空間給 OS | ❌（只標記可重用） | ✅（重寫整張 table） |
| 解決 table bloat | 部分 | 完全 |
| 需要 lock | 不需要 | 需要 **排他鎖** |
| 速度 | 快 | 慢 |

`VACUUM FULL` 實際上是把整張 table **重寫一遍**，只保留 live tuple，所以：

```
Before: [dead][live][dead][dead][live][dead][live]  → 大量碎片
After:  [live][live][live]                          → 緊密排列
```

- Table 大小大幅縮減
- Page 數減少 → Query scan 的 I/O 大幅下降
- Index 也重建後效率恢復

---

## 後續建議

**立即監控**
```sql
-- 找出 long-running transaction
SELECT pid, now() - pg_stat_activity.query_start AS duration, query, state
FROM pg_stat_activity
WHERE state != 'idle'
ORDER BY duration DESC;

-- 監控 table bloat
SELECT schemaname, tablename, n_dead_tup, n_live_tup, last_autovacuum
FROM pg_stat_user_tables
ORDER BY n_dead_tup DESC;
```

**程式層面修正**
- 同步程式必須確保 transaction 有正確的 **COMMIT / ROLLBACK**
- 加上 **statement_timeout** 和 **lock_timeout** 防止 transaction 懸掛
- 考慮用 `idle_in_transaction_session_timeout` 自動殺掉殭屍 transaction

**DB 設定調整**
```sql
-- 超過 5 分鐘沒動作的 transaction 自動斷開
SET idle_in_transaction_session_timeout = '5min';
```
