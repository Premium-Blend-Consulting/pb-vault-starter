# wiki/ — codified knowledge

This is where I keep things I'll re-read. SOPs, client briefs, runbooks, ruleset patterns.

## Structure

- `sprinklr/` — platform knowledge that applies across clients
- `clients/[name]/` — per-client briefs, templates, and quirks

## Rules for Claude

- When I reference a client by name, default to looking in `clients/[that-client]/CONTEXT.md` before doing anything else.
- For Sprinklr config questions, look in `sprinklr/` first.
- Treat each `CONTEXT.md` as more specific than this one. Local rules override.
