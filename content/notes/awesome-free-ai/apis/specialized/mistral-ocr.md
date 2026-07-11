# Mistral OCR (Multimodal Document Understanding)

Mistral OCR represents a significant development in document understanding, extracting structured data from complex documents, including equations and nested tables.

## 🚀 Key Specs (2026 Update)
- **Model Support**: OCR-Multimodal-1 (native).
- **Free Allowance**: Trial through "Le Chat" or initial $1 credits (approx 1,000 pages).
- **Data Protection**: Zero-retention for API endpoints.
- **Primary Strength**: Context-aware extraction, high accuracy with technical documents.

## 🗝 Link to Console
1. Visit [Mistral AI (mistral.ai)](https://mistral.ai/).
2. Navigate to "La Plateforme" and select OCR services.
3. Access your API key from the "API Keys" dashboard.

## 🛠 Usage Example (Python/Mistral)
```python
from mistralai.client import MistralClient

client = MistralClient(api_key="YOUR_KEY")
with open("document.pdf", "rb") as f:
    response = client.ocr(document=f)
print(response.content)
```

## 🔗 Official Links
- [Mistral AI OCR](https://mistral.ai/news/mistral-ocr/)
- [Documentation](https://docs.mistral.ai/capabilities/ocr/)
