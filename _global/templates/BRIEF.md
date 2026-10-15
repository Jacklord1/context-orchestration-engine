# BRIEF.md template

The durable mission of a project: what it is, who it serves, and
what "done" or "running well" looks like. It changes rarely. A
re-read six months in should still feel current.

## Template

```markdown
# {Project} — BRIEF

## What this is
{One paragraph in plain language. Spell out any acronym on first
use.}

## Who it serves
{The primary audience. For client work: the client and their end
users. For a product: the buyer and the user.}

## What done means
{For a finite project: the shipped state.
For ongoing work: what "running well" looks like.}

## Why this matters
{The stake. If you can't write a real reason, the project is
probably premature.}

## What this is NOT
{What it's often mistaken for, and why it deliberately isn't that.}

## Constraints
{Hard limits that shape every decision: budget, deadline, legal,
ethical, your own time.}

## Ask before
{Project-specific actions an AI must confirm first, on top of the
ones in PROFILE.}
```

## How to use it

- **Write once, edit rarely.** A BRIEF that changes weekly means
  the project lacks a stable mission, and that's the real problem.
- **Use it as the tie-breaker.** If a choice contradicts the BRIEF,
  either the choice is wrong or the BRIEF needs updating. A BRIEF
  update needs a DECISIONS entry.
- **Keep it under about 600 words.** Anything longer belongs in
  `specs/`.

## Common mistakes

- **Listing features.** Features belong in BACKLOG or specs.
- **Fluffy missions.** "We help people thrive" is useless; specific
  is harder and better.
- **Mixing "done" with "next".** Next things belong in BACKLOG.
