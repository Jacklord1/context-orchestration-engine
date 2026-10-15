# _global — DECISIONS

Decisions about the brain itself: new file types, changes to
conventions, template changes. Project decisions go in that
project's own `DECISIONS.md`.

Newest at the top. Add-only: never edit a past entry; write a new
one that references it by date.

## YYYY-MM-DD — Adopted the context orchestration engine

Started this brain from the context orchestration engine template:
seven files per project, a STATE snapshot read first, and a
write-back tail at the end of every session.

**Why:** {Your reason. For example: "Every AI chat started blank
and I was re-explaining the same projects every day."}

**Implications:**
- Every active project gets a folder with the seven canon files.
- Every session that changes anything ends with a tail block in
  `outputs/`.
- Changes to the conventions or templates are logged here first.
