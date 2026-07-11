# Cloudflare Workers AI

Cloudflare Workers AI allows you to run machine learning models, powered by GPUs, on Cloudflare’s global network.

## 🚀 Key Specs (2026 Update)
- **Model Support**: Llama 3.x, Mistral, Gemma, Qwen (Quantized versions).
- **Free Tier (Daily Limit)**: 10,000 Neurons per day (Approx. 10,000 requests/day for lightweight models).
- **Edge Deployment**: Extremely low latency for global users by running inference at the network edge.
- **Quantization Policy**: Most edge-deployed models are INT4/INT8 to optimize for edge hardware.

## 🗝 Setup
1. Log in to [Cloudflare Dashboard](https://dash.cloudflare.com/).
2. Go to **Workers & Pages** -> **Workers AI**.
3. Create a Worker or use the REST API via a Cloudflare API Token.

## 🛠 Usage Example (REST API)
```bash
curl -X POST "https://api.cloudflare.com/client/v4/accounts/$CF_ACCOUNT_ID/ai/run/@cf/meta/llama-3-8b-instruct" \
     -H "Authorization: Bearer $CF_API_TOKEN" \
     -d '{
       "messages": [{"role": "user", "content": "Hello edge AI!"}]
     }'
```

## 🔗 Official Links
- [Cloudflare Workers AI](https://workers.cloudflare.com/)
- [Model Catalog](https://developers.cloudflare.com/workers-ai/models/)
