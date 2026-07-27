---
name: dashboard
description: Modify or republish the Jarvis command-deck dashboard (a live, self-updating artifact). Use when Bryan asks to change the dashboard's design, sections, or behavior — it does NOT need manual data refreshes.
---

The dashboard is a **live console** — it fetches Gmail/Calendar/ClickUp data itself via the artifact `mcp` capability every time Bryan opens it. Never rewrite it with static numbers.

Permanent URL: **https://claude.ai/code/artifact/7646b433-4bfc-4526-9cc3-cb13f0b99669**
Source: `dashboard/jarvis-dashboard.html` (see `dashboard/README.md` for architecture).

To change it:
1. Edit `dashboard/jarvis-dashboard.html` — keep the HUD design language (dark ground, cyan/gold accents, mono labels) unless Bryan asks otherwise.
2. Load the `artifact-capabilities` skill before touching any `window.claude.mcp` code.
3. Republish with the Artifact tool, favicon "⚡". From a session that didn't publish it before, pass `url` with the address above. **Omit the `capabilities` parameter** so the stored connector grants carry forward — only restate them if the set of connectors/tools the page calls actually changes.
4. Commit the updated file to the repo.
