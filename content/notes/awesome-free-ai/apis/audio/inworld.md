# Inworld AI (Character & Voice Agents)

Inworld AI is designed for natural multi-turn AI conversations, focusing on character-based dialogue and low-latency response.

## 🚀 Key Specs (2026 Update)
- **Model Support**: TTS-1 Max, Character Engine v2.
- **Latency**: Sub-200ms real-time audio interaction.
- **Free Allowance**: Trial available with up to 10k character synthesis or 15 mins of dialogue.
- **Primary Strength**: Context-aware dialogue and fluid multi-turn voice interaction.

## 🗝 Link to Console
1. Visit [Inworld Studio](https://studio.inworld.ai/).
2. Create an account and name your workspace.
3. Access your API key from the "Developer" settings.

## 🛠 Usage Example (JS/Node)
```javascript
import { InworldClient } from "@inworld/nodejs-sdk";

const client = new InworldClient().setApiKey("YOUR_KEY");
const interaction = client.sendText("Hello AI character!");
console.log(interaction.text);
```

## 🔗 Official Links
- [Inworld.ai](https://inworld.ai/)
- [Documentation](https://docs.inworld.ai/)
