# SiliconFlow API (Free Model Aggregator)

SiliconFlow provides a unified API to access many open models(including Chinese LLMs like DeepSeek, Qwen and GLM) with a substantial free tier and high inference speeds.

## 🚀 Key Specs
- **Model Support**: `DeepSeek-V3`, `Qwen-2.5`, `GLM-4-9B`, `Mistral-7B`, etc.
- **Initial Free Credits**: Daily free models or credits ($5 bonus for new users).
- **Speed**: GPU-optimized for sub-second latency.
- **Style**: Fully OpenAI API compatible.

## 🗝 How to get an API Key
1. Visit [SiliconFlow Platform (siliconflow.cn)](https://siliconflow.cn/).
2. Register and go to **API Keys**.
3. Create a secret key.

## 🛠 Usage Example (Python/OpenAI Library)
```python
from openai import OpenAI

client = OpenAI(
    api_key="<SiliconFlow API Key>",
    base_url="https://api.siliconflow.cn/v1"
)

response = client.chat.completions.create(
    model="deepseek-ai/DeepSeek-V3", 
    messages=[{"role": "user", "content": "What is the capital of China?"}],
    stream=False
)
print(response.choices[0].message.content)
```

## 🔗 Official Links
- [SiliconFlow AI Home](https://siliconflow.cn/)
- [API Documentation](https://docs.siliconflow.cn/introduction)
