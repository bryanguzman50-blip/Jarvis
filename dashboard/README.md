# Jarvis Dashboard — Live Console

**Live at:** https://claude.ai/code/artifact/7646b433-4bfc-4526-9cc3-cb13f0b99669
(private to Bryan's Claude account; find it anytime under Artifacts at claude.ai)

`jarvis-dashboard.html` is the committed source of the published artifact. The page is **self-updating**: it declares the `mcp` runtime capability, so when Bryan opens it, it calls his connectors directly with his credentials. No Claude model runs — viewing it and using the console costs no usage.

## Panels
Live tiles (pipeline count, needs-action, unread, today's calendar), the Active Leads list with next actions, filtered inbox signal (subjects link straight to the Gmail thread), today's events, and connector status.

## Console commands

| Command | Connector call | Writes? |
|---|---|---|
| `brief` | — (composed from loaded panels) | no |
| `inbox` / `inbox from maria` | `search_threads` | no |
| `pipeline` | cached `clickup_filter_tasks` | no |
| `today` / `this week` | `list_events` | no |
| `draft an email …` | `create_draft` | draft only |
| `add event … tomorrow at 3pm` | `create_event` | yes, confirmed |
| `delete event …` | `delete_event` | yes, confirmed |
| `move … to friday at 2pm` | `update_event` | yes, confirmed |
| `note on [lead]: …` | `clickup_create_comment` | yes, confirmed |
| `new lead 123 Main St - Sarah` | `clickup_create_task` | yes, confirmed |
| `mao 200k arv 35k repairs` | none — local arithmetic | no |
| `help` / `cancel` | — | no |

Every write shows a preview and waits for `yes`. Ambiguous event/lead names offer a numbered pick list. Email is **draft-only** by design — nothing sends.

## Voice
**Every reply is spoken aloud by default**, along with its detail block where that's the substance (lists, previews) — the MAO arithmetic table and the help listing are shown but not read. The 🔊 button mutes/unmutes and the choice persists in `localStorage`. Uses `speechSynthesis`, preferring an en-GB voice ("Daniel"). The 🎙 TALK button works on desktop Chrome; **iOS Safari blocks microphone access inside artifact frames**, so on iPhone use the keyboard's dictation key instead — the button explains this when it's refused.

## Republishing
Only needed for design/logic changes. Use the Artifact tool on this same file path (from the original session) or pass `url` with the address above. **Omit `capabilities` when republishing** unless the set of connector tools the page calls has actually changed — omitting carries the stored grants forward.
