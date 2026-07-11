# LM Studio (GUI Local LLM)

LM Studio is the best GUI for discovering and running GGUF models on MacOS, Windows, and Linux.

## 🚀 Key Features (2026 Update)
- **Built-in Model Browser**: Search and download models directly from Hugging Face.
- **Hardware Acceleration**: Automatic GPU detection and management (CUDA / MPS).
- **In-App Inference**: Chat with models using an integrated desktop UI.
- **OpenAI Compatible**: Start a local server with a single click.

## 🛠 Local Setup
1. Download from [LM Studio](https://lmstudio.ai/).
2. Open the app and search for "Llama 3.3" or "Gemma 3".
3. Download a Q4_K_M (4-bit) quantization for best performance.

## 🗝 API Server Usage (Port 1234)
```bash
curl http://localhost:1234/v1/chat/completions \
  -H "Content-Type: application/json" \
  -d '{
    "model": "your-model-id",
    "messages": [{"role": "user", "content": "Explain quantum physics."}]
  }'
```

## 🔗 Official Links
- [LM Studio](https://lmstudio.ai/)
- [Discord Community](https://discord.gg/lmstudio)
