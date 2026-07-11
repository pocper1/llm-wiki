# Cerebras Cloud (WSE-3 Inference)

Cerebras Cloud provides free access to flagship open-weight models using their Wafer-Scale Engine (WSE-3), offering high parallelization and token throughput.

## 🚀 Key Specs (2026)
- **Model Support**: GPT-OSS 120B, Llama 3 series, specialized engineering models.
- **Hardware Tier**: Wafer-Scale Engine (WSE-3) architecture.
- **Rate Limit (Free Tier)**:
  - **Daily Request Cap**: 14,400 RPD.
  - **Requests per Minute**: 30 RPM.
  - **Tokens per Minute**: 60,000 TPM (Higher throughput for batch tasks).
- **Primary Strength**: High concurrency and batch processing.

## 🗝 How to get an API Key
1. Visit [Cerebras Cloud Console](https://cloud.cerebras.ai/).
2. Create an account.
3. Generate a key from the "API Keys" section.

## 🛠 Usage Example (Python)
```python
from openai import OpenAI

client = OpenAI(
    base_url="https://api.cerebras.ai/v1",
    api_key="YOUR_CEREBRAS_API_KEY",
)

response = client.chat.completions.create(
    model="llama-3.1-70b",
    messages=[{"role": "user", "content": "What is parallel computing?"}]
)
print(response.choices[0].message.content)
```

## 🔗 Official Links
- [Cerebras Cloud](https://cloud.cerebras.ai/)
- [Documentation](https://docs.cerebras.ai/)
