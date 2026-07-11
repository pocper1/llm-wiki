# ElevenLabs (High-Fidelity TTS)

ElevenLabs is arguably the leader in natural-sounding text-to-speech with advanced multilingual support.

## 🚀 Key Specs (2026 Update)
- **Model Support**: Eleven v3 Multilingual, v2 Turbo, v2 English.
- **Free Allowance**: 10,000 characters per month.
- **Languages**: 29+ languages standard, with v3 Multilingual covering over 100 on high-fidelity tiers.
- **Primary Strength**: #1 ranked quality in blind human evaluations for real-world voice synthesis.

## 🗝 How to get an API Key
1. Sign up at [ElevenLabs.io](https://elevenlabs.io/).
2. Login and navigate to "Profile" -> "API Keys" to generate your key.
3. Check "Voice Lab" to clone or select existing voices.

## 🛠 Usage Example (Python SDK)
```python
import elevenlabs

audio = elevenlabs.generate(
    text="Hello world! My name is Eleven.",
    voice="Bella",
    model="eleven_multilingual_v3"
)
elevenlabs.save(audio, "output.mp3")
```

## 🔗 Official Links
- [ElevenLabs.io](https://elevenlabs.io/)
- [Documentation](https://elevenlabs.io/docs)
