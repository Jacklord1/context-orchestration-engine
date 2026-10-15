# CONVENTIONS

The rules block, written for an AI to load at session start. Read
it top to bottom before doing any work in this repo.

## Session start

1. Read `_global/PROFILE.md`, which says who the owner is and how
   they work.
2. Read the project's `STATE.md`.
3. If the work touches tech, also read the project's `STACK.md`.
4. Load other files only when the task needs them:
   - Tier 2, when relevant: `BRIEF`, `ARCHITECTURE`, `RUNBOOK`,
     `BACKLOG`.
   - Tier 3, on demand: `DECISIONS`, old `outputs/`, `specs/`.
5. If STATE is `_To be populated_` or clearly stale, say so and ask
   before acting.

Don't load every file in a project. STATE is small on purpose.

## Session end

Every session that changed anything ends with these writes:

1. **The tail block** goes to
   `<project>/outputs/<YYYY-MM-DD>-<slug>.md`. Its shape is in
   `_global/prompts/session-end.md`: Result, Verified, Open, Next
   prompt.
2. **STATE.md** is overwritten as an updated snapshot. Keep "What
   this is" word for word and revise the other sections. Point
   "Last session outcome" at the tail you just wrote.
3. **DECISIONS.md** gets a new entry if a real choice was made.
4. **BACKLOG.md** has finished items moved to a dated Done section.

If you can't write to the repo, output those files in full so the
human can commit them.

## Never

- **Never fabricate.** `_To be populated_` means the owner hasn't
  filled it in, so ask. Don't invent plausible content.
- **Never write secrets.** API keys, passwords, tokens and private
  URLs never go in this repo. You may record a key's *name* (for
  example `STRIPE_API_KEY`) and where its value lives (for example
  "in the password manager").
- **Never edit past DECISIONS entries.** Add a new entry that
  references the old one by date.
- **Never claim something is verified that you didn't observe.**
  "Verified" means you ran it or saw it. If you couldn't check
  something, put it under Open.

## STATE.md rules

- Snapshot, not diary. Target ≤500 tokens, hard cap 800.
- Two dates, and they mean different things:
  - `_Updated:_` means someone wrote the file.
  - `_Last verified:_` means someone checked its claims against
    reality.
  Only bump `_Last verified:_` after listing the project's
  `outputs/`, checking "Where we are" against the world, and
  confirming the "Last session outcome" link resolves.
- If STATE is over the cap, prune before you add. History moves to
  DECISIONS or `outputs/`.

## Canon rules

- Each project has seven files: `STATE / DECISIONS / BRIEF /
  BACKLOG / STACK / ARCHITECTURE / RUNBOOK`. Shapes live in
  `_global/templates/`.
- Each project has three folders: `prompts/`, `outputs/` and
  `specs/`. A new file type or folder needs a DECISIONS entry
  first.
- Section headings are stable across projects. Don't rename
  `## Where we are` to `## Status`, because agents pattern-match on
  them.
- Folders whose names start with `_` are not projects (`_global/`,
  `_archive/`).
- Archive, don't delete. Retired projects move to `_archive/`.

## The brain is not a database

Live structured data stays in its own tool: task lists, CRM rows,
ticket queues, metrics and logs. STATE *links* to the tracker
rather than copying it. A brain that copies data ends up 80% stale
and loses its authority.

## Small jobs don't get a project

One-off work goes in the most related project's `outputs/`. Before
scaffolding a new project, ask: "Will I open STATE for this in
three months?" If the answer is no, it's an artefact, not a
project.

## Where things go

| Thing | Goes in |
|-------|---------|
| What's true now | `STATE.md` |
| Why we chose X | `DECISIONS.md` |
| Mission, audience, definition of done | `BRIEF.md` |
| Next things to do | `BACKLOG.md` |
| Tools, services, accounts | `STACK.md` |
| How the parts connect | `ARCHITECTURE.md` |
| Recurring ops, tech and business | `RUNBOOK.md` |
| What happened in one session | `outputs/YYYY-MM-DD-slug.md` |
| Long versioned documents | `specs/<topic>-v<n>.md` |
| Prompts to reuse | `prompts/` |

## Commits

Only if the brain is a git repo (level 2 and up). At levels 0 and 1
it's a plain folder: save the files and stop. Don't run git unless
the person asks.

- One logical change per commit.
- Message format: `<project>: <what changed>`, for example
  `plant-swap: log decision on RSVP form`.
- If two sessions might be working on the same project at once,
  pull before writing STATE and re-read it just before you
  overwrite it.

## Style

- Plain markdown. Short paragraphs and scannable bullets.
- Relative links (`./STATE.md`), not absolute.
- Follow the language and tone preferences in `_global/PROFILE.md`.
