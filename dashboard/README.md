# Jarvis Dashboard — Live Console

**Live at:** https://claude.ai/code/artifact/7646b433-4bfc-4526-9cc3-cb13f0b99669
(private to Bryan's Claude account; find it anytime under Artifacts at claude.ai)

`jarvis-dashboard.html` is the committed source of the published artifact. The page is **self-updating**: it declares the `mcp` runtime capability, so when Bryan opens it, it calls his Gmail (`search_threads`), Google Calendar (`list_events`), and ClickUp (`clickup_filter_tasks`) connectors directly with his credentials, re-polling every few minutes while open. No Claude model runs — viewing it costs no usage.

**▶ SPEAK BRIEF** composes a spoken summary from the live data and reads it with the device's built-in British voice (`speechSynthesis`, prefers "Daniel"/en-GB).

Republishing: only needed for design changes. Use the Artifact tool on this same file path (from the original session) or pass `url` with the address above (from any other session). **Omit the `capabilities` parameter when republishing** — that carries the stored connector grants forward unchanged.

Known gap: the calendar's day-with-events response shape was unverified at build time (only the empty-day case could be observed safely); the renderer handles the common shapes defensively. If a day with events renders oddly, tell Jarvis and he'll fix it against the real payload.
