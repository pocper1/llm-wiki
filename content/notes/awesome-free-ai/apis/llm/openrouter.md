# OpenRouter

OpenRouter is a unified interface for hundreds of LLMs. It aggregates multiple providers into a single OpenAI-compatible API.

## 🚀 Key Specs (Feb 2026)
- **Free Model Inventory**: 24+ models including Llama 3.3 70B, Gemini 2.0 Flash Exp, GPT-OSS 120B, MiMo-V2, Qwen 3 Coder.
- **Context Window**: Variable (up to 1M with Gemini).
- **Default Rate Limit**: 20 RPM / 50 RPD (Free-only account).
- **Escalation Path**: One-time $10 top-up increases daily limit to 1,000 requests.
- **Universal Gateway**: Single OpenAI-compatible endpoint for falling back across providers.


## 🗝 Setup
1. Sign up at [OpenRouter.ai](https://openrouter.ai/).
2. Go to **Keys** and create a temporary secret key.
3. Check **Models** -> filter by "Free" to see models you can call without credits.

## 🛠 Usage Example (OpenAI library)
```python
from openai import OpenAI

client = OpenAI(
  base_url="https://openrouter.ai/api/v1",
  api_key="YOUR_OPENROUTER_KEY",
)

completion = client.chat.completions.create(
  model="liquid/lfm-40b:free",
  messages=[{"role": "user", "content": "What is OpenRouter?"}]
)
print(completion.choices[0].message.content)
```

## 🔗 Reference
- [OpenRouter Models](https://openrouter.ai/models)
- [Documentation](https://openrouter.ai/docs)
