---
name: dashboard
description: Refresh and republish the Jarvis command-deck dashboard with current pipeline, inbox, and calendar data. Use when Bryan says "update my dashboard", "refresh the dashboard", or invokes /dashboard.
---

Refresh the Jarvis dashboard at its permanent URL:
**https://claude.ai/code/artifact/7646b433-4bfc-4526-9cc3-cb13f0b99669**

1. Pull fresh data:
   - ClickUp space "Wholesaling CRM" (id 90141845888) — all active leads with stages.
   - Gmail `is:unread in:inbox` — total unread count, plus the handful of real (non-promo) items.
   - Google Calendar — today's and tomorrow's events (America/Chicago).
2. Edit `dashboard/jarvis-dashboard.html` **in place**: update the date stamp, the four stat tiles, the lead list (address, stage pill, next action), the inbox signal items, and the Systems panel if a connector's status changed. Do not change the design, layout, title, or favicon.
3. Republish with the Artifact tool, favicon "⚡". From this repo's original build session the same file path keeps the URL; from any other session pass `url` with the address above.
4. Confirm to Bryan in one line, with the link.
