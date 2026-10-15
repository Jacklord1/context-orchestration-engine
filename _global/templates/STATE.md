# STATE.md template

A fixed-size snapshot of what's true right now for a project. Every
session reads it first, so its size sets the cost of every session.

**Target ≤500 tokens. Hard cap 800.** If you're writing more, the
extra belongs in `DECISIONS.md`, `BRIEF.md`, `outputs/` or `specs/`.

## Template

```markdown
# {Project} — STATE
_Updated: YYYY-MM-DD by {you | agent | chat}_
_Last verified: YYYY-MM-DD — outputs/ listed, claims checked_

## What this is
One paragraph, the same every session. The elevator pitch.

## Where we are
3–5 bullets. Current reality only: no history, no reasoning, no
plans.

## Active focus
What's being worked on this week. 2–3 lines.

## Recent decisions (pointers only)
- YYYY-MM-DD: one-line summary → DECISIONS.md
- YYYY-MM-DD: one-line summary → DECISIONS.md
(The last 3–5 only.)

## Open threads
What's parked, blocked or waiting on someone. 2–3 bullets.

## Last session outcome
→ outputs/YYYY-MM-DD-slug.md

## Next prompt
The exact prompt to start the next session with, or
"TBD — needs {owner} to decide X".
```

## How to use it

- **Session start:** read it.
- **Session end:** overwrite it. Keep "What this is" word for word
  and revise everything else.
- **Never append.** If the new version is longer than the old one,
  something that should have moved out has stayed in.

## Updated is not verified

`_Updated:_` means someone wrote the file. `_Last verified:_` means
someone checked it against reality. A STATE can be rewritten every
session for months and still claim things that stopped being true.

Only bump `_Last verified:_` after you have:

1. **Listed the project's `outputs/`.** Run the listing; don't go
   from memory. If outputs holds work STATE never mentions, STATE
   is stale.
2. **Checked "Where we are" against the world.** Is the site up?
   Is the file at that path? Is the meeting booked?
3. **Confirmed "Last session outcome" resolves.** The file must
   exist.

If you can't verify a claim, mark it or drop it. A stale but honest
date is worth more than a fresh but fictional one, because the
stale one tells you to go and look.

## What goes here and what goes elsewhere

- **STATE:** what's true now, this week's focus, parked threads,
  the next prompt.
- **DECISIONS:** *why*. STATE points to entries by date and never
  copies the reasoning.
- **BRIEF:** the durable mission. STATE assumes it's been read.
- **outputs/:** what happened in a session. STATE links the latest
  and doesn't summarise it.
- **specs/:** long documents. STATE names the current version.

## Token budget

| Section | Target |
|---------|--------|
| What this is | ~80 |
| Where we are | ~120 |
| Active focus | ~50 |
| Recent decisions | ~80 |
| Open threads | ~80 |
| Last session outcome | ~10 |
| Next prompt | ~80 |
| **Total** | **≤500 (cap 800)** |
