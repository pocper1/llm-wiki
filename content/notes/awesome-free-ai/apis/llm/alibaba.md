# Alibaba Cloud (DashScope)

Alibaba Cloud's DashScope provides access to the powerful Qwen (Tongyi Qianwen) series, which excels in coding and multilingual tasks.

## 🚀 Key Specs (2026 Update)
- **Model Support**: Qwen 3.5 Plus/Max, Qwen 3 Coder, Qwen-Speed-Lite.
- **Free Quota (New User)**: 1 million tokens free per model for 90 days.
- **Always Free Tier**: Qwen-Speed-Lite and Qwen-Long tokens are free for basic inference.
- **Primary Strength**: Coding and "Thinking" mode for deep reasoning (similar to o1).
- **Region**: International console (DashScope) available.

## 🗝 Setup
1. Sign up at [Alibaba DashScope (dashscope.aliyun.com)](https://dashscope.aliyun.com/).
2. Create an API Key in the "Workstation" -> "API Keys" section.

## 🛠 Usage Example (Python SDK)
```python
import dashscope

dashscope.api_key = "YOUR_API_KEY"
response = dashscope.Generation.call(
    model='qwen-max',
    prompt='Please write a Python script for a simple web crawler.'
)
print(response.output.text)
```

## 🔗 Official Links
- [Alibaba DashScope](https://dashscope.aliyun.com/)
- [Model Documentation](https://help.aliyun.com/product/2405523.html)
