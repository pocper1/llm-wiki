# Mistral AI (La Plateforme)

Mistral offers high-performance European-made models with a developer friendly free tier for prototyping and personal use.

## 🚀 Key Specs
- **Model Support**: Mistral-Large, Mistral-Next, Mixtral 8x22B, Pixtral (Multimodal).
- **Rate Limit (Free Tier)**: 
  - 1 Request Per Second (RPS) overall limit.
  - ~500k-1M Tokens Per Minute window.
- **Trial Allowance**: Free allowance for experimentation (no CC needed).

## 🗝 How to get an API Key
1. Sign up at [Mistral AI (console.mistral.ai)](https://console.mistral.ai/).
2. Go to **API Keys** and click **Create New Key**.
3. Note: If you don't add billing, your account will remain on the "Free Tier" limits.

## 🛠 Usage Example (Mistral SDK)
```python
from mistralai.client import MistralClient
from mistralai.models.chat_completion import ChatMessage

api_key = "YOUR_MISTRAL_API_KEY"
client = MistralClient(api_key=api_key)

messages = [ChatMessage(role="user", content="What is Mistral?")]
chat_response = client.chat(model="mistral-large-latest", messages=messages)

print(chat_response.choices[0].message.content)
```

## 🔗 Official Links
- [Mistral Console](https://console.mistral.ai/)
- [Pricing / Quota Table](https://console.mistral.ai/billing)
