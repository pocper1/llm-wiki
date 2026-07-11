# Qdrant (Vector Search Engine)

Qdrant is a vector similarity search engine that provides a production-ready service with a user-friendly API, focusing on Rust-based performance.

## 🚀 Key Specs (2026 Update)
- **Free Tier (Always Free)**: 1 GB Storage on Managed Cloud (unlimited write/read).
- **Core Technology**: Rust-based engine with payload filtering.
- **Primary Strength**: Developer experience and easy-to-use API for RAG applications.

## 🗝 Link to Console
1. Visit [Qdrant Cloud (qdrant.io)](https://qdrant.io/).
2. Create an account.
3. Access your API key and Cluster endpoint from the "Clusters" dashboard.

## 🛠 Usage Example (Python SDK)
```python
from qdrant_client import QdrantClient

client = QdrantClient(url="YOUR_CLUSTER_URL", api_key="YOUR_KEY")
client.upsert(
    collection_name="my_collection",
    points=[{"id": 1, "vector": [0.05, 0.61, 0.76]}]
)
```

## 🔗 Official Links
- [Qdrant.io](https://qdrant.io/)
- [Documentation](https://qdrant.tech/documentation/)
