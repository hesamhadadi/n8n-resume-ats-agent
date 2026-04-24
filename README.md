# n8n Resume ATS Agent

An AI-powered job-application workflow built as an [n8n](https://n8n.io) automation. Takes an uploaded resume PDF, analyzes it with Google Gemini, scores it against an ATS heuristic, and pushes matched roles to a Telegram bot.

## ✨ Features

- 📄 **PDF resume upload** — drop a resume into the workflow's webhook
- 🤖 **Gemini AI analysis** — parses the resume, extracts experience, skills, and seniority
- 🎯 **Job matching** — compares the resume against a pre-configured list of target roles
- 📊 **ATS score** — ranks each match with a readable score
- 📱 **Telegram notifications** — delivers top matches and the ATS report via a bot
- 💼 **Auto-apply hooks** — optional HTTP nodes for pushing applications to job boards

## 🧰 Stack

- [n8n](https://n8n.io) (self-hosted or cloud)
- Google Gemini API (text + multimodal)
- Telegram Bot API

## 🚀 Setup

1. Install / open n8n (self-hosted or n8n Cloud).
2. **Import** the workflow JSON in this repo:
   - n8n UI → *Workflows* → `…` → *Import from File*.
3. Add credentials:
   - `Gemini API` — Google AI Studio key
   - `Telegram` — bot token from @BotFather
4. Set environment variables (via n8n credentials or `.env`):

| Variable | Description |
|----------|-------------|
| `GEMINI_API_KEY` | Google Gemini API key |
| `TELEGRAM_BOT_TOKEN` | Telegram bot token |
| `TELEGRAM_CHAT_ID` | Destination chat/channel ID |

5. Activate the workflow.

## 🧩 How it works

```
Webhook (resume PDF)
  ↓
Gemini: extract skills, experience, summary
  ↓
Match against configured target roles
  ↓
ATS scoring (keyword coverage + seniority + experience fit)
  ↓
Telegram: send top matches + score breakdown
```

## Author

Hesam Hadadi — Senior Frontend Engineer · [hesamhaddadi.com](https://hesamhaddadi.com)
