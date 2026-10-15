# Templates

These are the shapes of the seven canon files. A new project copies
them (see `../prompts/new-project.md`).

Each template has three parts:

- **The template**, which is the block to copy.
- **How to use it**, with rules of thumb.
- **What goes here and what goes elsewhere**, which marks the line
  between neighbouring files. Most brain rot comes from blurring
  those lines.

| File | Shape |
|------|-------|
| [`STATE.md`](./STATE.md) | Fixed-size snapshot. Target ≤500 tokens. |
| [`DECISIONS.md`](./DECISIONS.md) | Dated add-only entries with Why and Implications. |
| [`BRIEF.md`](./BRIEF.md) | Mission, audience, definition of done. |
| [`BACKLOG.md`](./BACKLOG.md) | Imminent / Soon / Later / dated Done. |
| [`STACK.md`](./STACK.md) | Inventory of tools, services and accounts. |
| [`ARCHITECTURE.md`](./ARCHITECTURE.md) | How it fits together. |
| [`RUNBOOK.md`](./RUNBOOK.md) | Tech ops and business cadence. |

## Conventions shared by every template

- `_To be populated_` is the placeholder. Never fill a stub with
  invented content just to make it look started.
- Section headings are stable across projects. Agents
  pattern-match on them, so don't rename them per project.
- Relative links, not absolute.

## Changing a template

When a real project shows a template is missing a section, update
the template **and** log the change in `../DECISIONS.md`. The
templates are part of the canon, and canon changes need a record.
