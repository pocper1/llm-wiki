# vLLM (Production Local Serving)

vLLM is a high-throughput, memory-efficient serving engine for LLMs, utilizing PagedAttention to optimize Video RAM usage.

## 🚀 Key Specs (2026 Update)
- **Primary Strength**: High-throughput throughput with PagedAttention and FP8/INT8/INT4 support.
- **Hardware Tier**: Linux-first production deployments (NVIDIA GPUs / ROCm).
- **Core Technology**: Optimized for bulk processing and concurrent request handling.

## 🗝 Link to GitHub
1. Visit [vLLM GitHub](https://github.com/vllm-project/vllm).
2. Follow installation for Linux or use Docker.
3. Start a server with `python -m vllm.entrypoints.openai.api_server`.

## 🛠 Usage Example (OpenAI SDK)
```python
import openai

client = openai.OpenAI(base_url="http://localhost:8000/v1")
response = client.chat.completions.create(
    model="meta-llama/Llama-3.1-70B",
    messages=[{"role": "user", "content": "How does PagedAttention work?"}]
)
print(response.choices[0].message.content)
```

## 🔗 Official Links
- [vLLM.ai](https://vllm.ai/)
- [Documentation](https://docs.vllm.ai/)
