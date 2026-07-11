# Moonshot AI (Kimi) API

Moonshot AI's Kimi model is a leading Chinese LLM that pioneered long-context windows (up to 128k - 2M tokens) and excels in high-quality text understanding and code generation.

## 🚀 Key Specs
- **Model Support**: `moonshot-v1-8k/32k/128k`, `moonshot-v1-auto`.
- **Initial Free Credits**: **$15 Trial Credit** (roughly 1 million tokens of `moonshot-v1-8k`) for new users upon registration.
- **Special Features**: Massive context window, excellent Chinese nuance.
- **Style**: Fully OpenAI API compatible.

## 🗝 How to get an API Key
1. Visit [Moonshot Platform (platform.moonshot.cn)](https://platform.moonshot.cn/).
2. Register and create a secret API Key.
3. Access your $15 trial credit immediately after activation.

## 🛠 Usage Example (Python/OpenAI Library)
```python
from openai import OpenAI

client = OpenAI(
    api_key="<Moonshot API Key>",
    base_url="https://api.moonshot.cn/v1"
)

response = client.chat.completions.create(
    model="moonshot-v1-8k",
    messages=[{"role": "user", "content": "How are you doing today?"}],
    stream=False
)
print(response.choices[0].message.content)
```

## 🔗 Official Links
- [Moonshot AI Home](https://www.moonshot.cn/)
- [API Documentation](https://platform.moonshot.cn/docs/intro)
