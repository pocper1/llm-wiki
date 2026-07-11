# NVIDIA NIM API (Inference Microservices)

NVIDIA NIM provides optimized inference for a wide variety of open-source models, hosted by NVIDIA or deployable on your own hardware.

## 🚀 Key Specs
- **Model Support**: `Llama 3.3`, `Mistral-Large-2`, `Nemotron-4`, `Phi-3`, etc.
- **Free Allowance**: **40 RPM** (Requests Per Minute) via the NVIDIA Developer Program.
- **Cost**: Free for prototyping and research; requires enterprise license for production scale.
- **Style**: Fully OpenAI API compatible.

## 🗝 How to get an API Key
1. Join the [NVIDIA Developer Program (developer.nvidia.com)](https://developer.nvidia.com/login).
2. Visit the [NVIDIA API Catalog](https://build.nvidia.com/).
3. Select a model and click **Get API Key**.

## 🛠 Usage Example (Python/OpenAI Library)
```python
from openai import OpenAI

client = OpenAI(
  base_url="https://integrate.api.nvidia.com/v1",
  api_key="$NVIDIA_API_KEY"
)

completion = client.chat.completions.create(
  model="nvidia/llama-3.1-nemotron-70b-instruct",
  messages=[{"role":"user","content":"Explain how NIM works."}],
  temperature=0.5,
  top_p=1,
  max_tokens=1024,
  stream=False
)

print(completion.choices[0].message.content)
```

## 🔗 Official Links
- [NVIDIA NIM Home](https://developer.nvidia.com/nim)
- [API Catalog / Documentation](https://build.nvidia.com/)
