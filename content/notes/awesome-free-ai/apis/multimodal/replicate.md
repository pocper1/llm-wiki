# Replicate (Limited Free Credits)

Replicate lets you run any open source AI model with a cloud API. They provide a small amount of free credits to new users to test models.

## 🚀 Key Specs
- **Category**: Multimodal (Text, Image, Video, Audio).
- **Free Allowance**: Approximately $5 in free credits for the first two weeks.
- **Pay as You Go**: After trial, you pay only for what you use.
- **Best For**: Testing cutting-edge research models (e.g., Flux.1, SDXL, Video Gen).

## 🗝 Setup
1. Sign up at [Replicate.com](https://replicate.com/).
2. Grab your API Token from **Settings** -> **Account**.

## 🛠 Usage Example (cURL)
```bash
curl -X POST -H "Authorization: Token $REPLICATE_API_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"version": "your-model-version", "input": {"prompt": "a sunset"}}' \
  https://api.replicate.com/v1/predictions
```

## 🔗 Official Links
- [Replicate Pricing](https://replicate.com/pricing)
- [Model Directory](https://replicate.com/explore)
