# Session start

Paste this to open a session on a project when your tool doesn't
load `CONVENTIONS.md` automatically, for example a fresh chat.

## The prompt

```
We're working on the `{project}` project in my brain repo.

Before anything else:
1. Read _global/PROFILE.md and CONVENTIONS.md.
2. Read {project}/STATE.md. If the work is technical, also read
   {project}/STACK.md.
3. Tell me in 3–5 bullets what you understand the current state to
   be, and anything in STATE that looks stale or contradictory.
4. If STATE has a "Next prompt", ask whether that's what we're
   doing today.

Don't load other files until the task needs them.
```

## Why it's shaped like this

- **Step 3 is the check.** If the AI's summary is wrong, STATE is
  unclear, and you'll find out in the first minute rather than an
  hour in.
- **Step 4 closes the loop.** The last session left a next prompt,
  so use it.
- **"Don't load other files" protects the budget.** STATE is small
  so every session is cheap. Loading the whole project defeats the
  point.
