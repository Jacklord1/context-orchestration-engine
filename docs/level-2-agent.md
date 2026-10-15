# Level 2 — Chat plus a coding agent

**You get:** an agent (Claude Code, Codex, Cursor or similar) that
reads STATE at the start of a session and writes back and commits
at the end, with no copy-paste.
**You need:** level 1, plus a coding agent and the repo cloned
locally.
**Setup time:** about 10 minutes.

## How it works

```
chat (planning)  ──handoff prompt──►  agent (doing)
      ▲                                   │
      │ reads                             │ reads STATE, works,
      │                                   │ writes tail + STATE,
      └────────── the brain repo ◄────────┘ commits
```

Chat plans and writes a handoff
([`_global/prompts/handoff.md`](../_global/prompts/handoff.md)).
You paste it into the agent. The agent does the work and the
write-back. Chat reads the result next time.

## Setup

1. **Clone the brain** somewhere stable, for example `~/brain`.
2. **Let the loader do its job.** `CLAUDE.md` and `AGENTS.md` at
   the repo root point the agent at `CONVENTIONS.md`. Agents that
   read those files pick it up automatically when started inside
   the repo.
3. **Connect your code repos to the brain.** Your projects' code
   usually lives in other repos. Add a short block to each code
   repo's own `CLAUDE.md` or `AGENTS.md`:

   ```markdown
   ## Brain
   This repo's canon lives at ~/brain/{project}/. At session start
   read ~/brain/CONVENTIONS.md and ~/brain/{project}/STATE.md. At
   session end, do the write-back from
   ~/brain/_global/prompts/session-end.md and commit it in the
   brain repo (not this one).
   ```

   Now an agent working in the code repo keeps the brain current
   too.
4. **Allow the agent to commit to the brain repo** if your tool
   asks for permission per command.

## The daily loop

1. Plan in chat. End the chat with a handoff prompt.
2. Paste the handoff into the agent.
3. The agent works, then writes the tail and STATE and commits.
4. Push. If chat syncs from GitHub, it now sees the update.

Small jobs can skip chat: open the agent and say "read STATE for
{project}, then {task}".

## Tips

- **Push after each session.** Chat reads what's on GitHub, not
  your laptop.
- **One agent per project at a time.** Two sessions overwriting the
  same STATE will lose one of them. If you run agents in parallel,
  give them different projects.
- **Check the Verified section.** Agents are tempted to write
  "tests pass" without running them. The conventions forbid it, but
  read it anyway.
- **Use one commit per write** with a `project:` prefix, so
  `git log -- plant-swap/` becomes a project history.

## When to move up

Move to [level 3](./level-3-shared.md) when you want chat itself to
write back, for example when you do strategy sessions on your phone
or in a desktop app with no agent nearby.
