# DECISIONS.md template

The add-only log of choices made on a project. Each entry is dated,
names the decision, and records *why* and *what it implies*. This is
the file that stops an AI from re-suggesting the option you already
rejected.

## Template

```markdown
# {Project} — DECISIONS

Newest at the top. Add-only.

## YYYY-MM-DD — {short decision summary}

{1–3 short paragraphs: what prompted it, what the options were,
what was chosen.}

**Why:** {The real reasoning. This is what future-you reads first.}

**Implications:**
- {What this changes about how we work}
- {What it rules out}
- {What has to stay true for it to hold}
```

## How to use it

- **Newest at the top**, so recent reasoning is the first thing
  you read.
- **Add-only.** Never edit a past entry. A correction or reversal
  is a new entry that names the old one by date.
- **Decisions, not events.** "Picked Postgres over SQLite" is a
  decision. "Deployed v0.3" is an event and belongs in `outputs/`.
- **Log rejected options too.** "We will NOT do X" is often the
  most valuable kind of entry.

## What's worth logging

- Choices of tool, vendor or approach where there were real
  alternatives.
- Scope cuts: what's deliberately out.
- Pricing, naming and positioning.
- Changes to process or conventions.
- Anything where future-you might ask "why on earth did we…?"

## What isn't

- Implementation detail. That belongs in code or `specs/`.
- Routine completions. Those belong in `outputs/` or the BACKLOG
  Done list.
- Speculation. Only log what has actually been decided.

## When it gets long

Optionally, once a quarter, move entries older than about 90 days
to `DECISIONS-archive.md` in the same folder. Log that you did it.
