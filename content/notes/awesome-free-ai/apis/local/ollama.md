# Ollama (Local LLM API)

Ollama is the easiest way to run Large Language Models (LLMs) locally on your GPU/CPU with an OpenAI-compatible API.

## 🚀 Features
- **Privacy**: No data leaves your machine.
- **No Limit**: Free, unlimited inference. 
- **Model Gallery**: Supports Llama 3.2, Mistral, Gemma 2, Phi-3, and more.
- **OpenAI Compatibility**: Host your own `/v1/chat/completions` endpoint.

## 🛠 Local Setup (Desktop)
1. Download from [Ollama.com](https://ollama.com/download).
2. Run `ollama run llama3.2` to pull your first model.

## 🐳 Docker Deployment
Use our [docker-compose template](../../examples/docker-compose/ollama-api.yml) to run it as a service:
```bash
docker compose -f examples/docker-compose/ollama-api.yml up -d
```

## 🗝 API Usage (Port 11434)
```bash
curl http://localhost:11434/api/generate -d '{
  "model": "llama3.2",
  "prompt": "Why is the sky blue?"
}'
```

## 🔗 Links
- [Ollama Model Gallery](https://ollama.com/library)
- [Official GitHub](https://github.com/ollama/ollama)
