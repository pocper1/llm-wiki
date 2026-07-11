# iFlyTek Spark (Xinghuo)

iFlyTek Spark is highly regarded for its performance in coding, math, and rapid generation speeds.

## 🚀 Key Specs (2026 Update)
- **Model Support**: Spark 4.0 Ultra, Spark Max, Spark Lite.
- **Spark Lite**: Permanently free to use for individual and commercial trials.
- **Spark Max (Enterprise Bonus)**: 100 million free tokens on first enrollment for initial enterprise testing.
- **Primary Strength**: Coding assistance (iFlyCode) and ultra-fast throughput.

## 🗝 Link to Console
1. Visit [iFlyTek Spark (xfyun.cn/sparkapi)](https://xinghuo.xfyun.cn/sparkapi).
2. Login and go to "Workstation" -> "Apps Management" -> "Control Panel".
3. Apply for Spark Lite and Spark Max free trials.

## 🛠 Usage Example (WebSocket/SDK)
```python
# iFlyTek uses a custom WebSocket protocol, but Lite is easily accessible through the Spark-Web API.
from spark_sdk import SparkClient

client = SparkClient(api_key="YOUR_KEY", api_secret="YOUR_SECRET")
response = client.chat(model="spark-lite", message="Tell me about the spark model.")
print(response)
```

## 🔗 Official Links
- [iFlyTek Spark Open Platform](https://xfyun.cn/sparkapi)
- [Model Documentation](https://www.xfyun.cn/doc/spark/index.html)
