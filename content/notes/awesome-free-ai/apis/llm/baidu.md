# Baidu ERNIE (Baidu Cloud / Puter.js)

Baidu ERNIE (Wenxin Yiyan) is China's leading LLM series, widely used for enterprise knowledge and multimodal tasks.

## 🚀 Key Specs (2026 Update)
- **Model Support**: ERNIE 4.5 Speed, ERNIE-Lite-8K, ERNIE-Speed-128K.
- **Access Tiers**:
  - **Baidu Qianfan Platform**: ERNIE Speed/Lite are completely free for all users.
  - **Puter.js Integration**: Open platform integration with "User-Pays" billing architecture.
- **Primary Strength**: Context understanding and enterprise-grade scale.

## 🗝 Link to Console
1. Visit [Baidu Cloud Qianfan (cloud.baidu.com)](https://cloud.baidu.com/product/wenxinworkshop).
2. Login and navigate to "Model Service" -> "Model Training & Management".
3. Check the "Free Models" section for ERNIE Speed/Lite.

## 🛠 Usage Example (cURL)
```bash
curl -L 'https://aip.baidubce.com/rpc/2.0/ai_custom/v1/wenxinworkshop/chat/ernie-speed-128k?access_token=YOUR_ACCESS_TOKEN' \
     -H 'Content-Type: application/json' \
     -d '{
       "messages": [{"role": "user", "content": "How to make Kung Pao Chicken?"}]
     }'
```

## 🔗 Official Links
- [Baidu Cloud (Qianfan)](https://cloud.baidu.com/product/wenxinworkshop)
- [ERNIE Documentation](https://cloud.baidu.com/doc/WENXINWORKSHOP/index.html)
