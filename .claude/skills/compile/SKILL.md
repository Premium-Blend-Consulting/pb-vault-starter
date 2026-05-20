---
name: compile
description: Promote raw/ notes into the wiki/clients/[client]/ structure. Use when the user runs "/compile [client]" or asks to "consolidate raw notes", "compile this week's notes", "promote raw findings to wiki", "update [client] context", or similar. Reads everything in raw/ that references the client, extracts decisions, themes, and action items, then updates the client's CONTEXT.md and adds new wiki entries.
---

# /compile — promote raw notes into the wiki

## Trigger

Fires when the user invokes `/compile [client-name]` or asks to:
- "compile this week's raw notes"
- "promote findings to wiki"
- "update [client]'s context"
- "consolidate the raw inbox"

## What you do

1. **Identify the client.** If the user passed a client name, use that. If not, ask: "Which client are we compiling for?"
2. **Find relevant raw files.** Scan `raw/` for files that:
   - Mention the client by name in title or body, OR
   - Tag the client in frontmatter, OR
   - Were filed since the last compile (check `wiki/clients/[client]/CONTEXT.md` for a "Last compiled" timestamp)
3. **Read them all.** Don't skim. Note specific decisions, themes, action items, escalations, and any new context about the client (people, preferences, restrictions).
4. **Update `wiki/clients/[client]/CONTEXT.md`.** Append new findings under appropriate sections (don't blow away existing structure):
   - If you learned new client preferences → "How they like communications"
   - If you learned new Sprinklr quirks → "Sprinklr quirks for this account"
   - If you found decisions or themes → add a "Recent decisions" or "Active themes" section
   - Update the "Last compiled: [date]" stamp at the top
5. **Create new wiki entries** if a topic deserves its own file (e.g., a new SOP, a runbook for a recurring issue). Path: `wiki/clients/[client]/[topic-slug].md`.
6. **Don't delete the raw files.** Add a small marker to each compiled raw file: `> Compiled: YYYY-MM-DD to wiki/clients/[client]/`
7. **Confirm to the user.** Summarize what you updated:

```
Compiled [N] raw notes for [client].
Updated: wiki/clients/[client]/CONTEXT.md
New: wiki/clients/[client]/[any-new-files].md
Marked raw files as compiled.
```

## Rules

- **Preserve existing wiki structure.** Append, don't rewrite. The user has invested in those files.
- **No PII or sensitive content** ever ends up in wiki/ (it shouldn't be in raw/ either, but double-check).
- If a raw note references multiple clients, surface that and ask whether to compile to each or just one.
- If you can't tell what a raw note is about, leave it. Don't guess.

## Example

User: `/compile starbucks`

You scan `raw/` and find three files from the last week mentioning Starbucks. You read them, extract:
- New theme: "loyalty program response time" — getting flagged by customers
- Decision: client wants more proactive sentiment flagging
- Action item: pull listening through 5/15

You update `wiki/clients/starbucks/CONTEXT.md` with these findings under appropriate sections, mark the raw files as compiled, and reply:

```
Compiled 3 raw notes for Starbucks.
Updated: wiki/clients/starbucks/CONTEXT.md (added "Recent themes" and "Open decisions")
Marked: raw/2026-05-15_sbx-listening-export.md, raw/2026-05-18_qbr-prep-notes.md, raw/2026-05-19_sbx-loyalty-flag.md
```
