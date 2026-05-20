---
name: status
description: Quick "where are we with this?" read-out for any topic — a client, a project, a research thread, a personal initiative. Use when the user runs "/status [topic]" or asks "where are we with [topic]", "what's the latest on [topic]", "give me a status on [topic]", "catch me up on [topic]", or similar. Pulls from the topic's folder in wiki/ — no raw reading, no re-explaining needed. Fast, structured summary.
---

# /status — quick topic read-out

## Trigger

Fires when the user invokes `/status [topic]` or asks:
- "where are we with [topic]"
- "what's the latest on [topic]"
- "catch me up on [topic]"
- "give me a status on [topic]"

The topic can be a client, a project, a research thread, a personal initiative — anything you've been building up in wiki/.

## What you do

1. **Identify the topic.** If the user passed a name, use that. If not, ask.
2. **Find the topic's folder.** Likely paths:
   - `wiki/clients/[name]/`
   - `wiki/projects/[name]/`
   - `wiki/research/[topic]/`
   - `wiki/personal/[topic]/`
   - `wiki/[domain]/[topic]/`
   If you can't find it, say so and offer to search broadly with the user.
3. **Read only from that folder's wiki entries.** Do NOT scan raw/. Do NOT scan output/. The wiki is the source of truth for "where we are." If it's not in wiki, it doesn't count for status.
4. **Compose a structured summary.** Keep it short. Format:

```markdown
**[Topic] · status as of [today's date]**

**Active themes / focus areas**
- [3-5 bullets from the topic's CONTEXT.md]

**Open decisions**
- [What's pending]

**Recent flags / blockers / escalations**
- [Anything flagged]

**Quick reference**
- [The 2-3 most important context items: tone, conventions, restrictions, key people]

**Last compiled:** [date from CONTEXT.md]
```

5. If the wiki is stale (last compile was more than a week ago), flag it:

```
⚠️ Wiki last compiled [N] days ago. Want me to run /compile [topic] first for a fresher read?
```

## Rules

- **Don't fabricate.** If the wiki is thin, say so. Don't fill gaps with guesses or pulls from raw.
- **Don't take longer than ~10 seconds.** This is a quick read-out, not a deep analysis.
- **No action items here.** Status is about state, not next steps. If the user wants next steps, that's a different ask.

## Examples by topic type

**Client status:** "Where are we with Starbucks?" → pulls from `wiki/clients/starbucks/`
**Project status:** "Status on the Q3 redesign?" → pulls from `wiki/projects/q3-redesign/`
**Research status:** "Catch me up on the AI tools research." → pulls from `wiki/research/ai-tools/`
**Personal status:** "Where are we on my self-review prep?" → pulls from `wiki/personal/self-reviews/q2-2026/`
