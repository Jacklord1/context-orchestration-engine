# New project

Use this to scaffold a new project folder.

## First, should it be a project at all?

Ask: **"Will I open STATE for this in three months?"**

- **Yes:** it has state worth tracking across sessions. Scaffold
  it.
- **No:** it's a one-off. Put it in the most related project's
  `outputs/` instead.

Half-dead project folders are the commonest way a brain rots.

## The prompt

```
Set up a new project in my brain repo with the slug `{slug}`.

1. Check the slug is lowercase kebab-case, at most 20 characters,
   and not already taken. If not, propose a fix and wait for me.
2. Read the seven templates in _global/templates/.
3. Create {slug}/ with STATE, DECISIONS, BRIEF, BACKLOG, STACK,
   ARCHITECTURE and RUNBOOK, copying each template's shape.
   Replace {Project} with the project name. Leave every section
   you can't fill as `_To be populated_`. Do not invent content.
   Create empty prompts/, outputs/ and specs/ folders (with a
   .gitkeep in each).
4. Ask me these five questions, one message, numbered:
   a. In one sentence, what is this?
   b. Who does it serve?
   c. What does done (or "running well") look like?
   d. What tools, services or accounts are already in play?
   e. Anything you must NOT do without asking me?
5. Fill BRIEF from a, b, c and e, and STACK from d. Write STATE's
   "What this is" from a.
6. Add a first DECISIONS entry: "Started this project" with the
   reason.
7. Add the project to "Active projects" in _global/PROFILE.md.
8. Commit as `{slug}: scaffold`, then do the session-end
   write-back.
```

## Notes

- **The five questions are the minimum.** They're enough for a
  useful BRIEF and nothing more, so don't let the AI pad it out.
- **STACK, ARCHITECTURE and RUNBOOK can stay as stubs** for a
  non-technical or early project. Stubs are honest; invented
  content isn't.
- **If the project doesn't fit the shape**, log a DECISIONS entry
  first rather than quietly making an exception.
