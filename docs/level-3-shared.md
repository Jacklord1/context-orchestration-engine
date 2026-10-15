# Level 3 — Shared write

**You get:** all three actors reading and writing the same brain
live. A chat on your phone can log a decision and the agent sees it
at its next session start.
**You need:** level 2, plus a way for your chat app to write files
in the repo, usually an MCP connector.
**Setup time:** from 30 minutes (an existing connector) to an
afternoon (building your own).

**This level is for people comfortable setting up developer
tools.** Levels 1 and 2 already give you most of the benefit.

This guide describes the pattern, not a specific product. Chat
apps, connectors and hosting options change fast, so check the
current docs for whatever you pick.

## What's an MCP connector?

MCP (Model Context Protocol) is a standard plug that lets a chat
app reach something outside itself, such as your calendar, a
database, or a folder of files. A **connector** is one of those
plugs, added in your chat app's settings.

At level 2, chat can only *read* a snapshot of your brain. A
connector with write access lets chat *save* to it as well, so
"wrap up" works from any chat, on any device.

## How it works

```
   chat ──MCP──┐                 ┌── agent (local clone)
               ▼                 ▼
          ┌─────────────────────────┐
          │   write path (commits)  │
          └────────────┬────────────┘
                       ▼
                 the brain repo
```

Every write, from either actor, becomes a git commit. That keeps
everything reversible and gives you a full history.

## Option A — use an existing connector

Many chat apps support MCP connectors. A connector that can read
and write files in a GitHub repo, such as a GitHub MCP server, will
do the job.

- Grant it access to **only the brain repo**, never your whole
  account.
- Each write it makes is a commit, so you get history for free.
- Update the chat project instructions to the level 3 option:
  "write each file through the connector".

The trade-off is that you depend on that connector's tools and
permissions, and some are read-heavy or clumsy at writing files.

## Option B — host a small brain API

If you run a home server or a small VPS, a tiny service in front of
your clone gives you full control. The shape is simple:

| Endpoint | Does |
|----------|------|
| `GET /list` | The file tree |
| `GET /{path}` | Read a file |
| `PUT /{path}` | Write a file, then `git commit` with a message from a header |
| `GET /search?q=` | Grep across the repo |

Wrap the same operations as MCP tools (`read`, `write`, `list`,
`search`, and optionally `append` and `edit`) so chat apps can use
them as a connector. Push to GitHub after each commit, or on a
timer, so local agents can pull.

Because each PUT commits, nobody has to think about git: chat and
agents just write files, and the history takes care of itself.

### Security, which matters at this level

You're exposing a write path to your working notes on the internet.

- **Authenticate everything.** Use an API key or OAuth at minimum.
  If your provider publishes the address ranges its connectors call
  from, allowlist them at your proxy as an extra layer, not as the
  only one.
- **Never expose your machine directly.** Use a tunnel or reverse
  proxy that makes outbound connections only, and expose this one
  service, nothing else.
- **Allowlist paths.** Refuse writes outside project folders and
  refuse anything under `.git/`.
- **Keep the repo private.** The secrets rule (names only) is your
  safety net if something leaks, not permission to be careless.
- **Keep the history.** No force-push, no history rewrites. Every
  write being a commit is what makes a bad write a one-line revert.

## Rules that matter more once everyone can write

- **Re-read STATE just before overwriting it.** Two actors can now
  write the same file minutes apart.
- **DECISIONS is add-only.** With three writers, editing history is
  how you lose track of who decided what.
- **Run the health check monthly**
  ([`_global/prompts/health-check.md`](../_global/prompts/health-check.md)).
  More writers means faster drift.
