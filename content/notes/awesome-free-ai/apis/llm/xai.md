# xAI Grok API
2: 
3: xAI offers powerful reasoning models with a strategic free-tier for developers who contribute to the network.
4: 
5: ## 🚀 Key Specs (2026 Update)
6: - **Model Support**: Grok 4.1 Fast, Grok 4, Grok 3.
7: - **New Policy**:
8:   - **Welcome Credit**: $25 one-time credit for new signups.
9:   - **Bonus Credit**: Monthly **$150 credit** for users who enable data-sharing.
10: - **Context Window**: 128K tokens.
11: - **Primary Strength**: Real-time context from the X platform and deep logical reasoning.
12: 
13: ## 🗝 How to get an API Key
14: 1. Sign up at [x.ai/api](https://x.ai/api).
15: 2. Navigate to the API dashboard.
16: 3. Verify your phone number to receive the $25 initial credit.
17: 
18: ## 🛠 Usage Example (Python)
19: ```python
20: import openai
21: 
22: client = openai.OpenAI(
23:   base_url="https://api.x.ai/v1",
24:   api_key="YOUR_XAI_KEY"
25: )
26: 
27: completion = client.chat.completions.create(
28:   model="grok-4-fast",
29:   messages=[{"role": "user", "content": "What is the latest AI trend on X?"}]
30: )
31: print(completion.choices[0].message.content)
32: ```
33: 
34: ## 🔗 Official Links
35: - [xAI Console](https://console.x.ai/)
36: - [Documentation](https://docs.x.ai/)
