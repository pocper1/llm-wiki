# Tencent Hunyuan API

Tencent Hunyuan is a powerful model developed by Tencent and is available on the Tencent Cloud platform.

## 🚀 Key Specs
- **Model Support**: `Hunyuan-lite` (**Always Free**), `Hunyuan-hub`, `Hunyuan-pro`.
- **Initial Free Credits**: **1M Tokens** shared trial package (for Pro models) / Permanent Free (Lite).
- **Cost**: Hunyuan-lite is free of charge.
- **Style**: Fully OpenAI API compatible (available on Tencent Cloud).

## 🗝 How to get an API Key
1. Visit [Tencent Cloud API Explorer (cloud.tencent.com)](https://console.cloud.tencent.com/hunyuan).
2. Create and copy your Tencent Cloud `SecretId` and `SecretKey`.
3. Some models are available through their unified platform.

## 🛠 Usage Example (Python/OpenAI Library)
```python
from openai import OpenAI

client = OpenAI(
    api_key="<Tencent Hunyuan API Key>",
    base_url="https://api.hunyuan.tencent.com/v1"
)

response = client.chat.completions.create(
    model="hunyuan-lite", # Always Free
    messages=[{"role": "user", "content": "How are you doing today?"}],
    stream=False
)
print(response.choices[0].message.content)
```

## 🔗 Official Links
- [Hunyuan Platform Home](https://hunyuan.tencent.com/)
- [API Documentation](https://cloud.tencent.com/document/product/1729)
