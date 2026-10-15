# STACK.md template

An inventory of the tools, services and accounts in play. It records
*what* is in use. *Why* belongs in DECISIONS, and *how the parts
connect* belongs in ARCHITECTURE.

A non-technical project can keep this short: the tools and accounts
it depends on.

## Template

```markdown
# {Project} — STACK

## Tools and tech

| Layer | Choice | Decided |
|-------|--------|---------|
| {e.g. Website} | {e.g. Astro on Netlify} | {YYYY-MM-DD → DECISIONS} |
| {e.g. Database} | {choice} | {date} |
| {e.g. Email} | {choice} | {date} |

## Services and accounts

| Service | Account | Cost / month | Owner |
|---------|---------|--------------|-------|
| {Service} | {which login or workspace} | {$} | {who} |

## Code repos

- `{repo}` — {URL}, {purpose}

## Secrets used (names only)

Values live in {your password manager}, never in this repo.

- `{KEY_NAME}` — {what it's for}
```

## How to use it

- **Inventory, not justification.** Each row points at the
  DECISIONS entry that chose it.
- **Update on change, not on speculation.** If something's only
  being evaluated, it belongs in BACKLOG until it's decided.
- **One row per concern**, so each thing can be swapped
  independently.

## Sanity checks

- Every paid service has a known monthly cost. If you can't put a
  number on it, you don't really know your stack.
- Every secret name resolves in your password manager. That's the
  most common thing to drift without anyone noticing.
