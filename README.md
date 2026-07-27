# J.A.R.V.I.S.

Bryan's personal AI — Claude Code wearing a British butler's tailcoat, wired into Gmail, Google Calendar, ClickUp (Wholesaling CRM), Notion, and Google Drive.

> "Very good, sir. Shall I pull up the pipeline?"

## Two ways to use him

**1. The dashboard + console — free, any browser, no Claude app.**
Open https://claude.ai/code/artifact/7646b433-4bfc-4526-9cc3-cb13f0b99669 (bookmark it; it's in your Artifacts list at claude.ai). It pulls your pipeline, inbox, and calendar *itself* every time you open it, and the command bar takes orders: draft an email, add/move/delete a calendar event, log a note on a lead, add a new lead, run offer math. No AI model runs, so it costs **zero usage/credits**. Full command list in `dashboard/README.md`.

**2. Conversation — when you need Jarvis to actually do something.**
Open Claude (mobile app, desktop, or claude.ai/code) on this **Jarvis** repo and just talk — tap the voice icon on mobile for hands-free. The persona, standing orders, and guardrails load automatically from `CLAUDE.md`. This is the mode that *thinks*, so it draws on your Claude subscription's usage — a quick brief or a drafted email is small; hours of open-ended chat is what adds up. Habit that keeps costs low: glance at the dashboard for status, open a conversation only when there's a task.

Things to say:

- *"Jarvis, morning brief"* (or `/brief`) — pipeline, inbox, calendar in 150 words
- *"Jarvis, what's hot in the pipeline?"* — deal-flow agent reviews ClickUp
- *"Jarvis, triage my inbox"* — inbox-scout finds the real mail under the promos
- *"Jarvis, draft a reply to Maria about 456 Oak Ave"* — scribe writes it in your voice
- *"Jarvis, pull comps for 123 Main St"* — researcher hits the web

## The build

| Piece | Where |
|---|---|
| Persona + standing orders | `CLAUDE.md` |
| The team (4 subagents) | `.claude/agents/` — inbox-scout, deal-flow, scribe, researcher |
| Your voice + business memory | `knowledge/` |
| `/brief` and `/dashboard` commands | `.claude/skills/` |
| Dashboard + console (live artifact) | link below + source in `dashboard/` |
| Morning routine | Daily 6:30 AM CT — brief waiting when you wake up |
| Weekly recap routine | Fridays 4:00 PM CT — stalled leads + Monday's priority |
| Remaining setup (voice, browser, socials) | `SETUP.md` |

**Dashboard:** https://claude.ai/code/artifact/7646b433-4bfc-4526-9cc3-cb13f0b99669

## Make him smarter

Jarvis is only as good as `knowledge/`. Paste real emails/texts you've written into `knowledge/voice.md`, fill in your buy box in `knowledge/business.md`, and he'll stop sounding like an AI and start sounding like you.
