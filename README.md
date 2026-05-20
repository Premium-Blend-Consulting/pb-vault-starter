# PB Vault Starter

The starter Claude vault for Premium Blend team members. A three-folder, context-routed personal knowledge system that pairs with Claude Cowork.

## What this is

A pre-built vault that gives Claude what it needs to be useful for *your* role at PB. Three folders, a few markdown files, three starter skills.

- **raw/** — inbox. Anything coming in.
- **wiki/** — codified knowledge. What you'll re-read.
- **output/** — finished deliverables.

Each folder has a `CONTEXT.md` or `README.md` that tells Claude what room it just walked into. Memory is persistent across chats because it lives in markdown, not in any one conversation.

## Install

Tell Claude:

> "Clone github.com/Premium-Blend-Consulting/pb-vault-starter into ~/pb-vault and walk me through pointing Cowork at it."

That's it. Claude clones, drops the structure at `~/pb-vault/`, and helps you add it as a Cowork project.

## Customize

1. Open `CLAUDE.md` at the root and fill in the bracketed sections (who you are, your day-to-day).
2. Open `wiki/clients/[client]/CONTEXT.md` and replace the demo Starbucks/AT&T examples with your actual book of business.
3. Don't worry about getting it perfect. The system improves as you use it.

## Skills

Three slash commands ship with the vault, under `.claude/skills/`:

- **`/raw [note]`** — drop a thought into `raw/` with a date-prefixed filename
- **`/compile [client]`** — promote notes from `raw/` into `wiki/clients/[client]/`
- **`/status [client]`** — quick read-out of where you are on a client, pulling from `wiki/`

Build your own — they're just markdown files in `.claude/skills/[skill-name]/SKILL.md`.

## What never goes in the vault

- Client PII (real names + emails in lists)
- Signed contracts, NDAs, SOWs
- Passwords, API keys, tokens
- Unreleased financials

The leak test: *"If this leaked publicly tomorrow, would I be on a call with HR or Vince?"* If yes, don't put it here.

## Questions

Slack: `#claude-help`. Or DM Joe.

---

Built by the AI & Innovation Pod, Premium Blend.
