# BACKLOG.md template

An ordered list of what's next. Position is priority: the top item
is next. It's not a kanban board.

## Template

```markdown
# {Project} — BACKLOG

Top = next.

## Imminent
- **{One-line title}** — {context: what, why now, any constraint}.

## Soon
- **{Title}** — {context}.

## Later
- **{Title}** — {context}.

## Done (YYYY-MM-DD)
- {What was done} → outputs/YYYY-MM-DD-slug.md
```

## How to use it

- **Imminent, Soon and Later are the only tiers.** If an item
  doesn't fit one of them, it's either premature (it belongs in the
  BRIEF) or already done.
- **Use one bold title per item**, with the context after a dash on
  the same line.
- **Done sections are dated and pile up at the bottom.** Prune old
  ones every quarter.
- **An item bigger than about half a day** should be split, or
  given its own handoff prompt in `prompts/`.

## What goes here and what goes elsewhere

- **BACKLOG:** any piece of work with a clear outcome.
- **DECISIONS:** the *choice* a backlog item produces. "Decide on a
  payment provider" lives here until it's decided; then the choice
  goes in DECISIONS and the item moves to Done.
- **RUNBOOK:** recurring work. "Send the monthly newsletter" isn't a
  backlog item.
- **A real task tracker:** if you already use one, BACKLOG can just
  link to it. The brain is not a database.

## What isn't a backlog item

- Vague intentions. "Improve the site" isn't one; "Add a
  photo-upload step to listings" is.
- Other people's work with no clear handover.
