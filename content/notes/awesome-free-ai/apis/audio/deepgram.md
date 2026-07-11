# Deepgram (Ultra-low Latency Audio)

Deepgram is a hardware-accelerated audio processing engine, focusing on real-time transcription and voice generation for agentic bots.

## 🚀 Key Specs (2026 Update)
- **Model Support**: Nova-3 (STT), Aura-2 (TTS), Whisper-Cloud.
- **Latency**: Sub-300ms typical for full-round-trip real-time agents.
- **Trial Credits**: $200 initial credits for new developers (often enough for 100+ hours).
- **Primary Strength**: Lowest latency in the market for high-volume voice-to-voice apps.

## 🗝 Link to Console
1. Visit [Deepgram Console](https://console.deepgram.com/).
2. Create an account.
3. Generate a project API key from the "API Keys" dashboard.

## 🛠 Usage Example (cURL TTS)
```bash
curl -X POST "https://api.deepgram.com/v1/speak?model=aura-asteria-en" \
     -H "Authorization: Token $DEEPGRAM_API_KEY" \
     -H "Content-Type: application/json" \
     -d '{"text": "Hey there! This is a low-latency voice speaking."}' \
     --output speech.mp3
```

## 🔗 Official Links
- [Deepgram](https://deepgram.com/)
- [Documentation](https://developers.deepgram.com/)
