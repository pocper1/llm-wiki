# ByteDance Doubao API (Volcengine)

Doubao is a powerful model developed by ByteDance and is available via the Volcengine platform.

## 🚀 Key Specs
- **Model Support**: `Doubao-pro`, `Doubao-lite`, `Doubao-Coder`.
- **Initial Free Credits**: **5亿 (500M) Tokens** for personal users (no expiry).
- **Rate Limit**: 2M daily tokens for personal accounts.
- **Context Window**: 32k - 128k depending on the model.
- **Style**: Fully OpenAI API compatible (v4).

## 🗝 How to get an API Key
1. Visit [Volcengine Console (console.volcengine.com/ark)](https://console.volcengine.com/ark).
2. Register and create a personal account (required for the free 500M credit).
3. Under **Model Management**, find and create a secret API Key.

## 🛠 Usage Example (Python SDK)
```python
from volcenginesdkarkruntime import Ark

client = Ark(api_key="your_api_key")

response = client.chat.completions.create(
    model="ep-2024...", # Your specific endpoint ID
    messages=[{"role": "user", "content": "Tell me a joke."}],
    stream=False
)
print(response.choices[0].message.content)
```

## 🔗 Official Links
- [Doubao AI Home](https://www.doubao.com/)
- [API Documentation](https://www.volcengine.com/docs/8230/1221447)
