# DeepSeek API (OpenAI Compatible)

DeepSeek provides high-performance models (V3, R1) for free for initial development and offers generous monthly token allowances.

## 🚀 Key Specs
- **Model Support**: DeepSeek-V3, DeepSeek-Chat, DeepSeek-Coder.
- **Initial Free Credits**: Usually 1M~3M Initial Tokens during trial period. 
- **Cost**: Extremely low (among the cheapest in the industry for paid usage if credits run out).
- **Style**: Fully OpenAI API compatible.

## 🗝 How to get an API Key
1. Visit [DeepSeek Platform (platform.deepseek.com)](https://platform.deepseek.com/).
2. Register and go to **API Keys**.
3. Create a secret key.

## 🛠 Usage Example (Python/OpenAI Library)
```python
from openai import OpenAI

client = OpenAI(
    api_key="<DeepSeek API Key>",
    base_url="https://api.deepseek.com"
)

response = client.chat.completions.create(
    model="deepseek-chat",
    messages=[{"role": "user", "content": "Tell me a joke about AI."}],
    stream=False
)
print(response.choices[0].message.content)
```

## 🔗 Official Links
- [DeepSeek AI Home](https://www.deepseek.com/)
- [API Documentation](https://api-docs.deepseek.com/)
