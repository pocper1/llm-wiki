# Pollinations.ai (Truly Free)

Pollinations.ai is a community-driven project that provides free image generation and large language model access **without requiring an API Key or registration**.

## 🚀 Key Specs
- **Media**: Image generation (Stable Diffusion based) and LLM (meta-llama-3-70b-instruct).
- **No API Key**: Just use cURL or URL parameters.
- **Limit**: Soft rate limits; high frequency requests may be throttled.
- **Cost**: 100% Free.

## 🖼 Image Generation (GET request)
```bash
curl "https://image.pollinations.ai/prompt/a%20futuristic%20city%20with%20neon%20lights?width=1024&height=1024&nologo=true"
```

## 💬 Text Generation
```bash
curl -X POST https://text.pollinations.ai/ \
  -H "Content-Type: application/json" \
  -d '{
    "messages": [
      {"role": "user", "content": "Hello, how are you?"}
    ],
    "model": "openai"
  }'
```

## 🔗 Official Links
- [Pollinations.ai Web](https://pollinations.ai/)
- [GitHub Repo](https://github.com/pollinations/pollinations)
