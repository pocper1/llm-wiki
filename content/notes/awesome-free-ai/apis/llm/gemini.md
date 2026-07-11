# Google Gemini API

Google Gemini 1.5 provides one of the most powerful and generous free tiers in the industry, featuring a massive 1M context window.

## 🚀 Key Specs (2026 Update)
- **Model Support**: Gemini 3.1 Pro/Flash, Gemini 2.5 series, Gemma 3.
- **Rate Limit (Free Tier)**:
  - **Gemini 3.1 Flash-Lite**: 1,000 RPD, 15 RPM.
  - **Gemini 3.1 Pro**: 100 RPD, 10 RPM.
- **Context Window**: 1,000,000 tokens benchmark.
- **🔞 Restriction**: **Not available** in EU, UK, and Switzerland free tiers.
- **Data Privacy**: Input/Output used for training in the free tier.


## 🗝 How to get an API Key
1. Go to [Google AI Studio (aistudio.google.com)](https://aistudio.google.com/).
2. Login with your Google Account.
3. Click **Get API key** on the sidebar.

## 🛠 Usage Example (Python)
```python
import google.generativeai as genai
import os

genai.configure(api_key="YOUR_GEMINI_API_KEY")
model = genai.GenerativeModel('gemini-1.5-flash')

response = model.generate_content("Give me a list of 3 underrated travel destinations.")
print(response.text)
```

## 🔗 Official Links
- [Google AI Studio](https://aistudio.google.com/)
- [Gemini Documentation](https://ai.google.dev/docs)
