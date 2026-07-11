---
title: 免費 AI API 大補貼 (Awesome Free AI API)
---

精選的 **50+ 個免費 AI API** 清單、用法範例以及 **Docker 自架模板**。  
無論你是在做 Side Project、進行原型設計，還是純粹想探索最強大的 GenAI，這份清單都能幫你**不用花一毛錢**就輕鬆上手。 💸

---

## 🆕 最近更新

- **2026-03-20**: 根據 2026 年最新市場動態全面更新。包含 Gemini 3.1 額度下調、Groq Llama 4 Scout、xAI Grok 新政策及 OpenAI GPT-4o 正式退役資訊。 🚀

---


## 🌟 快速上手推薦

| 分類 | 首選推薦 | 優勢 | 連結 |
|----------|------------|---------|:----:|
| **LLM (推理最快)** | [Groq](./apis/llm/groq.md) | LPU 驅動 (Llama 3.3 70B 每秒 300+ Tokens)。 | [前往](https://console.groq.com/) |
| **LLM (智能最強)** | [Google Gemini](./apis/llm/gemini.md) | 3.1 Pro/Flash，1M 上下文窗口業界標竿。 | [前往](https://aistudio.google.com/) |
| **LLM (整合介面)** | [OpenRouter](./apis/llm/openrouter.md) | 提供 24+ 款免費模型，包含 Llama 3.3 與 Gemini 3.1。 | [前往](https://openrouter.ai/) |
| **圖像生成** | [SiliconFlow](https://siliconflow.cn/) | Flux 2 Schnell (1-4 步極速生成)。 | [前往](https://siliconflow.cn/) |
| **本地執行** | [Ollama](./apis/local/ollama.md) | 支援 GGUF/Q4_K_M，優化 KV 快取。 | [前往](https://ollama.com/) |

> [!IMPORTANT]
> **2026 戰略佈景報告**: 深入了解當前市場動態、硬體加速 (LPU/WSE) 及基礎設施韌性，請閱讀 [2026 戰略佈景報告 (英文版)](./STRATEGIC_LANDSCAPE_2026.md)。部分廠商 (如 OpenAI) 已於 2/16 進行型號更換，請開發者注意遷移。

---

## 📚 目錄

- [🤖 1. LLM APIs (雲端文字生成)](#-1-llm-apis-雲端文字生成)
- [💻 2. 本地 LLM 引擎與工具](#-2-本地-llm-引擎與工具)
- [🖥️ 3. 硬體配備需求 (VRAM/RAM)](#-3-硬體配備需求-vramram)
- [🎨 4. 圖像生成](#-4-圖像生成)
- [🔊 5. 語音相關 (TTS / STT)](#-5-語音相關-tts--stt)
- [🔍 6. 專業領域 (OCR / 翻譯 / 搜尋)](#-6-專業領域-ocr--翻譯--搜尋)
- [💾 7. 向量資料庫與基礎設施](#-7-向量資料庫與基礎設施)
- [⌨️ 8. AI 輔助編程工具 (Coding Assistants & IDEs)](#️-8-ai-輔助編程工具-coding-assistants--ides)

---

## 🤖 1. LLM APIs (雲端文字生成)

透過免費層級或試用額度存取大型語言模型。已針對 **2026 年初** 進行更新。

| 供應商 | 模型 / 層級 | 免費額度與速率限制 | 註冊? | 連結 |
|:---|:---|:---|:---:|:---|
| **[Google Gemini](./apis/llm/gemini.md)** | Gemini 3.1 / 2.5 系列 | 100 - 1,000 RPD / 1M 上下文 | 是 | [前往](https://aistudio.google.com/) |
| **[Groq](./apis/llm/groq.md)** | Llama 3.3 / 4 Scout | 1,000 - 14,400 RPD (極速 LPU) | 是 | [前往](https://console.groq.com/) |
| **[Cerebras](./apis/llm/cerebras.md)** | GPT-OSS 120B / Llama 3.1 | 30 RPM / 14,400 RPD (高吞吐) | 是 | [前往](https://cloud.cerebras.ai/) |
| **[SambaNova](./apis/llm/sambanova.md)** | Llama 3 (LPU加速) | 30M 免費 Token ($5 試用金) | 是 | [前往](https://cloud.sambanova.ai/) |
| **[xAI Grok](./apis/llm/xai.md)** | Grok 4.1 Fast / 4 | **新：** 註冊送 $25，開啟共享每月送 $150 | 是 | [前往](https://x.ai/api) |
| **[OpenRouter](./apis/llm/openrouter.md)** | 24+ `:free` 模型 | 20 RPM / 50 RPD (加值 $10 可升至 1000) | 是 | [前往](https://openrouter.ai/) |
| **[GitHub Models](./apis/llm/github-models.md)** | GPT-5.4 mini / Llama 4 | 10-15 RPM / 50-150 RPD | 是 | [前往](https://github.com/marketplace/models) |
| **[NVIDIA NIM](./apis/llm/nvidia-nim.md)** | Llama 3.3, Nemotron | 40 RPM (開發者計劃) | 是 | [前往](https://developer.nvidia.com/nim) |
| **[DuckDuckGo](./apis/llm/duckduckgo.md)** | Llama 4 / GPT-5 mini | **完全免費** (透過 Duck.ai 匿名) | 否 | [前往](https://duck.ai/) |
| **[Mistral AI](./apis/llm/mistral.md)** | Mistral Small 3 / OCR | 1 RPS / 1B Tokens (實驗計劃) | 是 | [前往](https://console.mistral.ai/) |
| **[MiniMax](./apis/llm/minimax.md)**          | abab 6.5s / 7       | 1000萬 Tokens (新用戶) / 100萬 試用      | 是 | [前往](https://platform.minimaxi.com/)        |
| **[智譜 AI (GLM)](./apis/llm/zhipu.md)**     | GLM-4-Flash / Plus  | **Flash 模型永久免費** / 2500萬 Tokens    | 是 | [前往](https://open.bigmodel.cn/)             |
| **[騰訊混元](./apis/llm/hunyuan.md)**          | Hunyuan-lite / Pro  | **Lite 模型永久免費** / 100萬 Tokens       | 是 | [前往](https://cloud.tencent.com/product/hunyuan) |
| **[豆包 (字節跳動)](./apis/llm/doubao.md)**      | Doubao-pro / lite   | 個人 5億 Tokens (無期限) / 每日 200萬    | 是 | [前往](https://www.volcengine.com/product/doubao) |
| **[矽基流動 (SiliconFlow)](./apis/llm/siliconflow.md)** | 模型整合器 (V3/Q3) | 10-20 款免費模型 (DeepSeek/Qwen)       | 是 | [前往](https://siliconflow.cn/)               |
| **[Kimi (月之暗面)](./apis/llm/moonshot.md)**     | moonshot-v1-8/32k   | 註冊送 $15 額度 (~100萬 Tokens)         | 是 | [前往](https://platform.moonshot.cn/)         |
| **[通義千問 (DashScope)](./apis/llm/alibaba.md)** | Qwen 3.5 / 3.0 | 1M Tokens (90天) / Qwen-Speed 永久免費 | 是 | [前往](https://dashscope.aliyun.com/) |
| **[DeepSeek](./apis/llm/deepseek.md)** | V3 / R1 | 1M~3M 初始額度 + 每月贈送 | 是 | [前往](https://www.deepseek.com/) |
| **[訊飛星火 (Spark)](./apis/llm/iflytek.md)** | Spark 4.0 Ultra | Lite: 永久免費 / Max: 1億 tokens | 是 | [前往](https://xinghuo.xfyun.cn/sparkapi) |
| **[百度千帆 / Puter](./apis/llm/baidu.md)** | ERNIE 4.5 / Puter.js | 「用戶自付」模式，開發者免付費 | 是 | [前往](https://puter.com/) |
| **[Cloudflare](./apis/llm/cloudflare.md)** | Workers AI | 每天 10,000 Neurons | 是 | [前往](https://workers.cloudflare.com/) |
| **[Together AI](https://www.together.ai/)** | 模型庫極廣 | $25 免費額度 (每月充能 $5) | 是 | [前往](https://www.together.ai/) |
| **[Hugging Face](./apis/llm/huggingface.md)** | Serverless 推理 | 共享速率限制 (300+ 模型) | 是 | [前往](https://huggingface.co/) |
| **[Cohere](https://cohere.com/)** | Command-R/R+ | 20 RPM / 每月 1,000 次請求 | 是 | [前往](https://cohere.com/) |
| **[AI21 Labs](https://www.ai21.com/)** | Jamba 系列 | $10 額度 (3 個月) | 是 | [前往](https://www.ai21.com/) |

> [!NOTE]
> 想看這些模型目前的排名嗎？請參考 [LMSYS Chatbot Arena Leaderboard](https://arena.ai/leaderboard)。

---

## 💻 2. 本地 LLM 引擎與工具

在自己的硬體上執行模型，享受 100% 隱私且零成本。

| 工具 | 平台支援 | 特點 | 連結 |
|:---|:---|:---|:---|
| **[Ollama](./apis/local/ollama.md)** | MacOS/Win/Linux | 最易上手、模型庫極豐富、支援 CLI 與 API。 | [前往](https://ollama.com/) |
| **[LM Studio](./apis/local/lm-studio.md)** | MacOS/Win/Linux | 最強圖形介面，輕鬆下載並執行 GGUF 模型。 | [前往](https://lmstudio.ai/) |
| **[vLLM](./apis/local/vllm.md)** | Linux/Docker | 高吞吐量、PagedAttention 技術，生產環境首選。 | [前往](https://github.com/vllm-project/vllm) |
| **oMLX** | MacOS (M1-M4) | 專為 Apple Silicon 優化，支援持久化 KV 快取。 | [前往](https://github.com/jundot/omlx) |
| **LocalAI** | Linux/Docker | OpenAI API 的替代品，支援圖像、語音、文字。 | [前往](https://localai.io/) |
| **GPT4All** | MacOS/Win/Linux | 重視隱私的桌面軟體，無需 GPU 也能跑。 | [前往](https://gpt4all.io/) |
| **AnythingLLM** | Desktop/Docker | 全方位的 RAG 解決方案，支援在地化執行。 | [前往](https://useanything.com/) |

> [!NOTE]
> 不確定該選哪個？請查看 [2026 本地引擎深度對比指南 (英文)](./apis/local/comparison.md)。

---

## 🖥️ 3. 硬體配備需求 (VRAM/RAM)

根據 2026 年標準整理的建議硬體配備。

| 模型規模 | 量化程度 | 顯存 (VRAM) 需求 | 建議硬體 (2026) | 效能預期 |
| :---: | :---: | :---: | :--- | :--- |
| **7B - 9B** | Q4_K_M (4-bit) | 5 - 8 GB | RTX 4060 (8GB) | ~40 tokens/sec |
| **14B - 20B** | Q4_K_M (4-bit) | 10 - 15 GB | RTX 4070 Ti (12GB) | ~30 tokens/sec |
| **27B - 35B** | Q4_K_M (4-bit) | 20 - 24 GB | RTX 4090 / 5090 | ~25 tokens/sec |
| **70B+** | Q4_K_M (4-bit) | 40 - 50 GB | Mac Studio (64GB+) | ~8-15 tokens/sec |

> [!TIP]
> **4-bit 量化** (Q4_K_M) 是當前黃金標準。它能減少約 75% 的顯存佔用，同時保持 95-98% 的模型智慧。

---

## 🎨 4. 圖像生成

透過這些開放 API 生成高品質的 AI 圖片。

| 供應商 | 類型 / 模型 | 免費條款與限制 | 註冊? | 連結 |
|:---|:---|:---|:---:|:---|
| **SiliconFlow** | Flux 2 Schnell | 贈送初始額度 / 1-4 步極速 | 是 | [前往](https://siliconflow.cn/) |
| **Google** | Gemini 3 Pro Img | 整合在 AI Studio 中 | 是 | [前往](https://aistudio.google.com/) |
| **[Pollinations](./apis/image/pollinations.md)** | 圖像/文字 | 完全開放，不需 API Key | 否 | [前往](https://pollinations.ai/) |
| **HF ZeroGPU** | Flux/SDXL | 共享算力，小時限制 | 是 | [前往](https://huggingface.co/spaces) |
| **Leonardo.ai** | Canva 整合版 | 每天 150 Tokens (自動更新) | 是 | [前往](https://leonardo.ai/) |
| **Adobe Firefly** | 企業級/免費版 | 需 Adobe 帳戶 | 是 | [前往](https://firefly.adobe.com/) |
| **DeepAI** | 文字轉圖像 | 速率限制的免費使用 | 否 | [前往](https://deepai.org/) |
| **AI Horde** | 社群驅動 | 100% 免費 / 共享算力 | 可選 | [前往](https://stablehorde.net/) |
| **OpenAI** | GPT Image 1.5 | $5 初始額度 (新帳號) | 是 | [前往](https://openai.com/) |
| **騰訊雲** | 混元 3.0 | 具備試用額度 / 中文提示詞優化 | 是 | [前往](https://hunyuan.tencent.com/) |
| **Replicate** | Flux, SDXL | $5 免費試用額度 | 是 | [前往](https://replicate.com/) |

---

## 🔊 5. 語音相關 (TTS / STT)

為你的應用程式加入極致音質或超低延遲的語音服務。

| 供應商 | 類型 | 免費額度 | 連結 |
|:---|:---|:---|:---|
| **[ElevenLabs](./apis/audio/elevenlabs.md)** | TTS (v3) | 每月 10,000 個字元 (品質王者) | [前往](https://elevenlabs.io/) |
| **[Deepgram](./apis/audio/deepgram.md)** | Nova-3 (STT) | $200 試用金 / 延遲極低 | [前往](https://deepgram.com/) |
| **[Inworld AI](./apis/audio/inworld.md)** | 智慧語音盒 | sub-200ms 對話延遲 ( trial) | [前往](https://inworld.ai/) |
| **AssemblyAI** | 語音轉文字 | 100+ 小時免費 / $50 額度 | [前往](https://www.assemblyai.com/) |
| **Google Cloud** | 雲端語音 | 每月 400 萬字元 (標準音) | [前往](https://cloud.google.com/text-to-speech) |
| **Azure Speech** | 多樣化語音 | 每月 500,000 字元 | [前往](https://azure.microsoft.com/) |
| **Amazon Polly** | 穩定輸出 | 每月 500 萬字元 (首年免費) | [前往](https://aws.amazon.com/polly/) |

---

## 🔍 6. 專業領域 (OCR / 翻譯 / 搜尋)

用於特定 AI 任務的專業 API。

| 供應商 | 任務 | 免费额度 | 連結 |
|:---|:---|:---|:---|
| **[Mistral OCR](./apis/specialized/mistral-ocr.md)** | OCR | 2026 新標竿，精準解析公式/表格 | [前往](https://mistral.ai/) |
| **DeepL / Google** | 翻譯 | 每月 500,000 個字元 | [前往](https://www.deepl.com/pro-api) |
| **Tavily AI** | AI 搜尋 | 每月 1,000 次搜尋 | [前往](https://tavily.com/) |
| **Exa AI** | AI 搜尋 | 每月 1,000 次搜尋 | [前往](https://exa.ai/) |
| **OCR.space** | OCR | 每月 25,000 次請求 | [前往](https://ocr.space/ocrapi) |

---

## 💾 7. 向量資料庫與基礎設施

你的 RAG 和長期記憶應用的核心支柱。

| 供應商 | 儲存空間 | 免費層級細節 | 連結 |
|:---|:---|:---|:---|
| **Pinecone** | Serverless | 不限 Namespace，按量計費免費額度 | [前往](https://www.pinecone.io/) |
| **[Qdrant](./apis/vector-db/qdrant.md)** | 1 GB | 託管雲 (永久免費 1GB) | [前往](https://qdrant.io/) |
| **MongoDB Atlas** | 512 MB | 共享叢集 / 支援向量索引 | [前往](https://www.mongodb.com/) |
| **Supabase** | 500 MB | 內建 pgvector 的 PostgreSQL | [前往](https://supabase.com/) |
| **Zilliz (Milvus)** | 5 GB | 企業級規模免費層級 | [前往](https://zilliz.com/) |
| **Weaviate** | Sandbox | 14 天免費試用沙盒 | [前往](https://weaviate.io/) |
| **Chroma** | OSS | 免費開源，開發者友好 | [前往](https://trychroma.com/) |

## ⌨️ 8. AI 輔助編程工具 (Coding Assistants & IDEs)

內建強大 AI 能力的開發環境與代理工具，為個人開發者提供免費額度。已針對 **2026 年初** 更新。

| 工具 | 核心模型 | 免費層級細節 | 平台 | 連結 |
| :--- | :--- | :--- | :--- | :--- |
| **Claude Code** | Claude 3.5 Sonnet | CLI 代理工具，研究性免費存取 | CLI | [前往](https://anthropic.com) |
| **Antigravity** | Google Frontier | 高級 Agentic 編程，具備深度 Context 推理 | IDE/CLI | [前往](#) |
| **Cursor** | Claude / GPT-4o | 2000 次自動補全 + 每月限量高級請求 | IDE | [前往](https://cursor.com/) |
| **Trae** | Gemini / Claude | 針對早期用戶提供動態免費額度 | IDE | [前往](https://trae.ai/) |
| **Windsurf** | Claude 3.5 / Flow | 整合式 Agentic Flow，按量免費額度 | IDE | [前往](https://codeium.com) |
| **GitHub Copilot** | GPT-4o / o1 / 4.o | 學生、教師與開源維護者免費 | 擴充元件 | [前往](https://github.com) |
| **GitHub Models** | Qwen-Coder / o1 | 在 VS Code / Codespaces 中免費原型設計 | 擴充元件 | [前往](https://github.com) |
| **Amazon Q** | Claude 3 / Titan | 個人開發者**免費層級** (AWS 優化) | 插件 | [前往](https://aws.amazon.com) |
| **Codeium** | 內容感知 SLM | **個人開發者永久免費** | 插件 | [前往](https://codeium.com) |
| **MarsCode** | 豆包編程模型 | 雲端 IDE 與擴充元件提供優厚免費額度 | IDE/Ext | [前往](https://marscode.com) |
| **OpenAI Codex** | Codex / GPT-4o mini | 多數 AI 編程工具的底層基礎技術 (經典指標) | API | [前往](https://openai.com/zh-Hant/codex/) |

---

**最後更新**: 2026-03-20 02:58:27 (GMT+8)
