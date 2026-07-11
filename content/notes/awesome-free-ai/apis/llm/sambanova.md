# SambaNova Cloud

SambaNova Cloud provides high-speed inference for open models leveraging their DataScale systems.

## 🚀 Key Specs (2026 Update)
- **Model Support**: Llama 3 series, high-speed open-weights.
- **Hardware Tier**: DataScale / RDUs (Reconfigurable Data Units).
- **Free Allowance**: $5 Credit (Approximately 30M free tokens).
- **Primary Strength**: Balance between inference speed and daily throughput.

## 🗝 How to get an API Key
1. Visit [SambaNova Cloud](https://cloud.sambanova.ai/).
2. Sign up and verify your email.
3. Access your API key from the dashboard.

## 🛠 Usage Example (Bash)
```bash
curl -X POST "https://api.sambanova.ai/v1/chat/completions" \
     -H "Authorization: Bearer $SAMBANOVA_API_KEY" \
     -H "Content-Type: application/json" \
     -d '{
       "model": "meta-llama/Llama-2-70b-chat",
       "messages": [{"role": "user", "content": "Tell me a joke."}]
     }'
```

## 🔗 Official Links
- [SambaNova Cloud](https://cloud.sambanova.ai/)
- [Documentation](https://docs.sambanova.ai/)
