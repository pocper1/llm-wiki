# Groq Cloud (Ultra-fast Inference)

Groq is known for its LPU (Language Processing Unit) which provides the fastest inference speeds for open models today.

## 🚀 Key Specs (2026 Update)
- **Model Support**: Llama 3.3 (70B), Llama 3.2 (8B-14B), Mixtral 8x22B, Whisper.
- **LPU Architecture**: Eliminates memory bandwidth bottleneck for low latency.
- **Rate Limit (Free Tier)**:
  - **Large Models (70B+)**: 1,000 RPD, 12,000 TPM.
  - **Medium Models (8B-14B)**: 14,400 RPD, 6,000 TPM.
  - **Whisper**: 2,000 RPD, 7,200 audio-secs TPM.
- **Account Policy**: Organizational-level rate limits (Shared across all keys).


## 🗝 How to get an API Key
1. Visit [Groq Cloud Console](https://console.groq.com/).
2. Create an account.
3. Navigate to **API Keys** and generate one.

## 🛠 Usage Example (cURL)
```bash
curl -X POST "https://api.groq.com/openai/v1/chat/completions" \
     -H "Authorization: Bearer $GROQ_API_KEY" \
     -H "Content-Type: application/json" \
     -d '{
       "model": "llama-3.3-70b-versatile",
       "messages": [{"role": "user", "content": "Explain quantum computing in 2 sentences."}]
     }'
```

## 🔗 Official Links
- [Groq Console](https://console.groq.com/)
- [Discord Community](https://discord.gg/groq)
