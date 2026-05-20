---
name: raw
description: Drop a quick note into the user's raw/ inbox folder. Use whenever the user says "/raw" or asks to "save this as a note", "drop this in raw", "file this for later", or similar. Auto-creates a date-prefixed markdown file. Zero ceremony — file it now, sort it later.
---

# /raw — drop a note into the inbox

## Trigger

Fires when the user invokes `/raw [optional note text]` or asks to:
- "drop this in raw"
- "save this as a note"
- "file this for later"
- "capture this"

## What you do

1. **Get the content.** If the user passed text after `/raw`, that's the note body. If they said "drop this" referencing the current conversation, summarize the relevant chunk in 1-2 sentences.
2. **Pick a slug.** 3-6 words, hyphenated, describes the topic. Lowercase.
3. **Pick the date.** Today's date in `YYYY-MM-DD` format.
4. **Write the file.** Path: `raw/[YYYY-MM-DD]_[slug].md`. Format:

```markdown
# [Topic — readable title]

[The note content. Plain markdown. Don't over-format.]

---
Captured: [timestamp]
Source: [if from a transcript / message / link, drop the source here]
```

5. **Confirm to the user.** One line: "Filed to `raw/[filename].md`."

## Rules

- Never edit existing raw/ files via this skill. New files only.
- If the slug collides with an existing file, append `-2`, `-3`, etc.
- Don't promote to wiki/ from here. That's `/compile`'s job.
- If the note is clearly client-specific, mention which client at the top of the file but still file it in `raw/` (not `wiki/clients/`).

## Example

User: `/raw the loyalty program sentiment shift this quarter is bigger than we thought — pull listening through 5/15`

You file `raw/2026-05-18_loyalty-sentiment-shift.md`:

```markdown
# Loyalty sentiment shift — Q2

The loyalty program sentiment shift this quarter is bigger than we thought. Pull listening through 5/15 to confirm.

---
Captured: 2026-05-18
```

Then respond: "Filed to `raw/2026-05-18_loyalty-sentiment-shift.md`."
