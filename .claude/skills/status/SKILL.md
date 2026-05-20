---
name: status
description: Quick what's-happening-with-[client] read-out. Use when the user runs "/status [client]" or asks "where are we with [client]", "what's the latest on [client]", "give me a status on [client]", "catch me up on [client]", or similar. Pulls from wiki/clients/[client]/ — no raw reading, no re-explaining needed. Fast, structured summary.
---

# /status — quick client read-out

## Trigger

Fires when the user invokes `/status [client-name]` or asks:
- "where are we with [client]"
- "what's the latest on [client]"
- "catch me up on [client]"
- "give me a status on [client]"

## What you do

1. **Identify the client.** If the user passed a name, use that. If not, ask.
2. **Read only from `wiki/clients/[client]/`.** Do NOT scan raw/. Do NOT scan output/. The wiki is the source of truth for "where we are." If it's not in wiki, it doesn't count for status.
3. **Compose a structured summary.** Keep it short. Use this format:

```markdown
**[Client] · status as of [today's date]**

**Active themes**
- [3-5 bullets from wiki/clients/[client]/CONTEXT.md "Recent themes" or "Active themes" section]

**Open decisions**
- [What's pending]

**Recent escalations / flags**
- [Anything in the wiki tagged as escalation or flagged]

**Quick reference**
- Tone: [what the client likes]
- Sprinklr quirks: [naming convention, custom fields]
- Restrictions: [any AI clauses or do-not-do rules]

**Last compiled:** [date from CONTEXT.md]
```

4. If the wiki is stale (last compile was more than a week ago), flag it:

```
⚠️ Wiki last compiled [N] days ago. Want me to run /compile [client] first for a fresher read?
```

## Rules

- **Don't fabricate.** If the wiki is thin, say so. Don't fill gaps with guesses or pulls from raw.
- **Don't take longer than ~10 seconds.** This is a quick read-out, not a deep analysis.
- **No action items here.** Status is about state, not next steps. If the user wants next steps, that's a different ask.

## Example

User: `/status starbucks`

You read `wiki/clients/starbucks/CONTEXT.md` and reply:

```
**Starbucks · status as of 2026-05-20**

**Active themes**
- Loyalty program response time slipping in Q2
- Sentiment shift on weekend mobile orders
- Competitor activity: Dunkin loyalty refresh

**Open decisions**
- Whether to expand ruleset scope for Q3

**Recent escalations / flags**
- High-profile mention 5/17 — spillover risk monitored

**Quick reference**
- Tone: warm, professional, never casual
- Sprinklr: SBX-[market]-[function]-[version]
- QBR: quarterly, 12-slide format, exec summary up front

**Last compiled:** 2026-05-18
```
