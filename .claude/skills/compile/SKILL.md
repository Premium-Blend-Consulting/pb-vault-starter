---
name: compile
description: Promote raw/ notes into structured wiki/ knowledge for any topic — a client, a project, a research thread, a personal initiative. Use when the user runs "/compile [topic]" or asks to "consolidate raw notes", "compile this week's notes", "promote raw findings to wiki", "update [topic] context", or similar. Reads everything in raw/ that relates to the topic, extracts decisions, themes, and action items, then updates the topic's CONTEXT.md and adds new wiki entries.
---

# /compile — promote raw notes into the wiki

## Trigger

Fires when the user invokes `/compile [topic]` or asks to:
- "compile this week's raw notes"
- "promote findings to wiki"
- "update [topic]'s context"
- "consolidate the raw inbox"

The topic can be anything: a client, a project, a research thread, a personal initiative, an internal workstream. The skill is the same; the destination folder varies.

## What you do

1. **Identify the topic.** If the user passed a name, use that. If not, ask: "Which topic are we compiling for?"
2. **Find the destination folder.** Look for an existing folder under `wiki/` that matches:
   - `wiki/clients/[name]/` for a client
   - `wiki/projects/[name]/` for an internal project
   - `wiki/research/[topic]/` for a research thread
   - `wiki/personal/[topic]/` for personal work (e.g. self-reviews, career planning)
   - `wiki/[domain]/` for any other top-level domain
   If no folder exists yet, create one in the most appropriate spot and seed it with a `CONTEXT.md`.
3. **Find relevant raw files.** Scan `raw/` for files that:
   - Mention the topic by name in title or body, OR
   - Tag the topic in frontmatter, OR
   - Were filed since the last compile (check destination `CONTEXT.md` for a "Last compiled" timestamp)
4. **Read them all.** Don't skim. Note specific decisions, themes, action items, escalations, and any new context (people, preferences, restrictions, source links).
5. **Update the destination `CONTEXT.md`.** Append new findings under appropriate sections (don't blow away existing structure). Update the "Last compiled: [date]" stamp at the top.
6. **Create new wiki entries** if a topic deserves its own file (e.g., a new SOP, a runbook, a research summary). Path: `wiki/[domain]/[topic]/[subtopic-slug].md`.
7. **Don't delete the raw files.** Add a small marker to each compiled raw file: `> Compiled: YYYY-MM-DD to wiki/[path]/`
8. **Confirm to the user.** Summarize what you updated.

## Rules

- **Preserve existing wiki structure.** Append, don't rewrite. The user has invested in those files.
- **No PII or sensitive content** ever ends up in wiki/.
- If a raw note references multiple topics, surface that and ask whether to compile to each or just one.
- If you can't tell what a raw note is about, leave it. Don't guess.

## Examples by topic type

**Client compile:**
```
User: /compile starbucks
You: Update wiki/clients/starbucks/CONTEXT.md with new themes, decisions, escalations.
```

**Project compile:**
```
User: /compile q3-redesign
You: Update wiki/projects/q3-redesign/CONTEXT.md with decisions, blockers, owner shifts.
```

**Research compile:**
```
User: /compile ai-tools-research
You: Update wiki/research/ai-tools/CONTEXT.md with findings, tools tested, recommendations.
```

**Personal compile:**
```
User: /compile self-review
You: Update wiki/personal/self-reviews/q2-2026/CONTEXT.md with wins, feedback received, projects shipped.
```
