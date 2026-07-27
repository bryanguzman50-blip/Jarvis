# Jarvis Setup — the Full Toolkit Checklist

Status of all 11 items from the "Build Your Own Jarvis" toolkit. ✅ = built and working. 🔑 = needs an account/API key only Bryan can create — each has exact steps below.

| # | Item | Status |
|---|---|---|
| 1 | Jarvis dashboard | ✅ Built — live artifact (link in README) + `dashboard/` in this repo |
| 2 | Talk to it + British voice | ✅/🔑 Voice mode works today; ElevenLabs voice needs an API key |
| 3 | Use your browser | 🔑 Install the Claude for Chrome extension |
| 4 | Track revenue (RevenueCat) | 🔑 Only relevant if you ship an app with subscriptions — skip for now |
| 5 | Auto-post content (Buffer) | 🔑 Needs a Buffer account + token |
| 6 | Instagram analytics | 🔑 Needs a Meta developer app + token |
| 7 | Read + run ads (Meta Ads) | 🔑 Connect the Meta Ads connector on claude.ai |
| 8 | Read your inbox (Gmail) | ✅ Connected and working |
| 9 | Answer customers in your voice | ✅ Built — `knowledge/` folder (fill in `voice.md` samples) |
| 10 | Team of specialized agents | ✅ Built — 4 subagents in `.claude/agents/` |
| 11 | Run it before you wake up | ✅ Built — daily 6:30 AM CT morning-brief Routine |

Also already connected beyond the toolkit: **Google Calendar, ClickUp, Notion, Google Drive**.

---

## 2. British voice (ElevenLabs)

Talking **to** Jarvis already works: tap the voice icon in the Claude mobile/desktop app, or `/voice` where available. For Jarvis to talk **back** in a proper British voice:

1. Create an account at [elevenlabs.io](https://elevenlabs.io) (free tier is fine to start) → Profile → **API key**, copy it.
2. Add the official ElevenLabs MCP server to Claude Code — in a terminal:
   ```bash
   claude mcp add elevenlabs -e ELEVENLABS_API_KEY=YOUR_KEY -- uvx elevenlabs-mcp
   ```
3. Pick a British voice in the ElevenLabs voice library (**Daniel** and **George** are the classic Jarvis-adjacent picks) and tell Jarvis: *"use the Daniel voice when you speak"*.
4. Then: "Jarvis, read me my morning brief" → he generates the audio.

## 3. Browser (Claude for Chrome)

Install the **Claude for Chrome** extension from claude.ai/chrome, sign in, and Jarvis can drive your browser — pulling leads from sites without APIs, filling forms, checking listings. Advanced alternative: Playwright MCP (`claude mcp add playwright -- npx @playwright/mcp@latest`).

## 5–7. Buffer / Instagram / Meta Ads

- **Buffer (auto-post):** create a Buffer account, connect your social profiles there, then add the Buffer MCP/connector on claude.ai → Settings → Connectors and authorize it. Then: "Jarvis, have scribe draft this week's posts and queue them in Buffer."
- **Instagram analytics:** requires a Meta developer app — developers.facebook.com → Create App → add Instagram Graph API → generate a long-lived access token for your IG business account → give the token to Jarvis in a session (never commit it to this repo).
- **Meta Ads:** claude.ai → Settings → Connectors → search "Meta Ads" → connect with your Meta Business account.

## Security notes

- **Never commit API keys or tokens to this repo.** Keys go in connector settings or MCP env vars only.
- Jarvis's standing orders (CLAUDE.md) already forbid sending email or moving money without your confirmation.
