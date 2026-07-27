# Jarvis Setup — the Full Toolkit Checklist

Status of all 11 items from the "Build Your Own Jarvis" toolkit. ✅ = built and working. 🔑 = needs an account/API key only Bryan can create — each has exact steps below.

| # | Item | Status |
|---|---|---|
| 1 | Jarvis dashboard | ✅ Built — **live console** (pulls Gmail/Calendar/ClickUp itself, zero credits) |
| 2 | Talk to it + British voice | ✅ Voice-in works in the Claude app; British voice-out works on the dashboard (built-in, no key). ElevenLabs premium voice: key received, needs 2-min desktop install below |
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

## 2. British voice

Three layers, cheapest first:

- **Voice in (works now):** tap the voice icon in the Claude mobile/desktop app while in the Jarvis repo.
- **Voice out, no key (works now):** the dashboard's **▶ SPEAK BRIEF** button uses your device's built-in British voice (on iPhone/Mac that's literally "Daniel (UK)"). Free, offline, zero setup.
- **Voice out, ElevenLabs quality:** Bryan's API key exists (kept out of this repo on purpose — **never commit it**). Two ways to wire it:
  1. **Desktop app (recommended):** in a terminal, `claude mcp add elevenlabs -e ELEVENLABS_API_KEY=<the key> -- uvx elevenlabs-mcp`, then tell Jarvis *"speak with the Daniel voice"*.
  2. **Cloud sessions (like this one):** at claude.ai → Code → this environment's settings, add env var `ELEVENLABS_API_KEY` and allow the domain `api.elevenlabs.io` in the network policy — the current policy blocks it, which is why Jarvis can't call ElevenLabs from the cloud yet.

## 3. Browser (Claude for Chrome)

Install the **Claude for Chrome** extension from claude.ai/chrome, sign in, and Jarvis can drive your browser — pulling leads from sites without APIs, filling forms, checking listings. Advanced alternative: Playwright MCP (`claude mcp add playwright -- npx @playwright/mcp@latest`).

## 5–7. Buffer / Instagram / Meta Ads

- **Buffer (auto-post):** create a Buffer account, connect your social profiles there, then add the Buffer MCP/connector on claude.ai → Settings → Connectors and authorize it. Then: "Jarvis, have scribe draft this week's posts and queue them in Buffer."
- **Instagram analytics:** requires a Meta developer app — developers.facebook.com → Create App → add Instagram Graph API → generate a long-lived access token for your IG business account → give the token to Jarvis in a session (never commit it to this repo).
- **Meta Ads:** claude.ai → Settings → Connectors → search "Meta Ads" → connect with your Meta Business account.

## Security notes

- **Never commit API keys or tokens to this repo.** Keys go in connector settings or MCP env vars only.
- Jarvis's standing orders (CLAUDE.md) already forbid sending email or moving money without your confirmation.
