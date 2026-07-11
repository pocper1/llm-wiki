# Zhipu AI (BigModel) - GLM-4 API

Zhipu AI (GLM) is a major Chinese provider that offers a high-performance model (GLM-4-Flash) that is **completely free forever** with a generous initial credit for other flagship models.

## 🚀 Key Specs
- **Model Support**: `GLM-4-Flash` (Always Free), `GLM-4-Plus`, `GLM-4V` (Vision).
- **Initial Free Credits**: **25.5M Tokens** for new users (for Plus models) or ~1M trial.
- **Context Window**: 128k - 1M depending on the model.
- **Style**: Fully OpenAI API compatible (v4).

## 🗝 How to get an API Key
1. Visit [Zhipu AI BigModel Platform (open.bigmodel.cn)](https://open.bigmodel.cn/).
2. Register an account and navigate to **API Keys**.
3. Copy your API Key (they also offer a special token generator).

## 🛠 Usage Example (Python SDK)
```python
from zhipuai import ZhipuAI

client = ZhipuAI(api_key="your_api_key")

response = client.chat.completions.create(
    model="glm-4-flash", # Always Free
    messages=[{"role": "user", "content": "What is the capital of France?"}],
    stream=False
)
print(response.choices[0].message.content)
```

## 🔗 Official Links
- [Zhipu AI AI Home](https://www.zhipuai.cn/)
- [API Documentation](https://open.bigmodel.cn/dev/api)
