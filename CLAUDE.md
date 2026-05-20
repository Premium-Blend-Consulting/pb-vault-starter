# PB Demo Vault

This is a sanitized example of how a PB team member could structure their personal Claude vault. Use it as a starting point, then customize.

## Who I am

[One sentence about your role at PB.]

## How my day-to-day looks

[2-3 sentences. Example: "I run managed services for two enterprise clients on Sprinklr. My week is meetings, dashboard config, weekly client reports, and escalations."]

## How I want Claude to work with me

- Always show me the plan before executing.
- Default to a professional tone.
- Flag assumptions clearly.
- Save outputs to `output/`. Filing rules below.

## Where things live

| Folder | Contents |
|---|---|
| `raw/` | Inbox. Brain dumps, transcripts, downloads, anything I haven't filed yet. |
| `wiki/` | Codified knowledge. SOPs, client briefs, ruleset references, anything I'll re-read. |
| `output/` | Finished deliverables. Decks, reports, anything I've shipped. |

## File naming

- Dated artifacts: `YYYY-MM-DD_topic-slug.md`
- Templates: `[topic]-template.md`
- Reports: `YYYY-MM_[client]-[type].md` (e.g. `2026-05_starbucks-monthly.md`)

## Routing rules

| If it's about... | Route to |
|---|---|
| A specific client | `wiki/clients/[name]/` |
| Sprinklr config or ruleset patterns | `wiki/sprinklr/` |
| A meeting note | `raw/`, then compile to `wiki/clients/[name]/` |
| A finished deliverable | `output/` |
| Quick brain dump | `raw/` — file later |

## What NOT to put in this vault

- Client PII (real names + emails in lists)
- Signed contracts, NDAs, SOWs
- Passwords, API keys, tokens
- Unreleased financials

If unsure, ask the leak test: "If this leaked publicly tomorrow, would I be on a call with HR or Vince?" If yes, don't put it here.
