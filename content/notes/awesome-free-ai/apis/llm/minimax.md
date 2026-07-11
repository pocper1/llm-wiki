# MiniMax API (OpenAI Compatible)

MiniMax provides low-latency, high-quality models (abab series) that excel in creative writing, role-playing, and logical reasoning.

## 🚀 Key Specs
- **Model Support**: `abab6.5s` (Speech/Fast), `abab7` (Latest/Smart).
- **Initial Free Credits**: **10M Tokens** for new users upon registration.
- **Context Window**: 128k - 256k depending on the model.
- **Style**: Fully OpenAI API compatible.

## 🗝 How to get an API Key
1. Visit [MiniMax Platform (platform.minimaxi.com)](https://platform.minimaxi.com/).
2. Register an account and navigate to **API Keys**.
3. Create a new secret key.

## 🛠 Usage Example (Python/OpenAI Library)
```python
from openai import OpenAI

client = OpenAI(
    api_key="<MiniMax API Key>",
    base_url="https://api.minimax.chat/v1"
)

response = client.chat.completions.create(
    model="abab6.5s-chat",
    messages=[{"role": "user", "content": "Write a short poem about the moon."}],
    stream=False
)
print(response.choices[0].message.content)
```

## 🔗 Official Links
- [MiniMax AI Home](https://www.minimaxi.com/)
- [API Documentation](https://platform.minimaxi.com/document/introduction)
