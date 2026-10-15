# Context Orchestration Engine

A plain-markdown, git-backed memory for working with AI. It lets
you, a chat assistant and a coding agent work on the same projects
without losing the thread between sessions.

There's no database, no vector store and no app. You get seven
files per project, a handful of rules, and the habit of writing
back at the end of every session.

## The problem

Every AI conversation starts blank. You paste context, re-explain
the project, and it re-suggests the thing you ruled out last week.

Connecting the AI to a drive full of documents doesn't fix that.
Now it can read everything, but nothing tells it:

- what to read **first**
- which document is **current** and which is a stale draft
- where to **write back** what it learnt

So it reads too much or too little, and the next chat starts blank
again. That's a context-management problem, not a storage problem.

## The idea

- **Every project gets the same seven files.** Any session, human
  or AI, knows where to look without being told.
- **One file is a small snapshot of what's true now.** `STATE.md`
  is read first by every session, and it's capped at about 500
  tokens, so loading context costs almost nothing.
- **Every session ends by writing back.** Update STATE, log any
  decisions, and leave the exact prompt the next session should
  start with.
- **It all lives in git.** Every change has a history and a diff,
  and you can see exactly what the AI changed and undo it.

## The three actors

| Actor | Role | Typical tool |
|-------|------|--------------|
| **You** | Owner. Sets direction, makes the calls, writes the BRIEF. | Your editor, GitHub |
| **Chat assistant** | Thinking partner. Reads the brain, plans, drafts handoff prompts. | Claude.ai, ChatGPT, desktop apps |
| **Coding agent** | Executor. Reads STATE, does the work, writes back. | Claude Code, Codex, Cursor |

The actors never talk to each other directly. The repo is the
shared whiteboard.

```
            ┌──────────────┐
            │     You      │  direction, decisions
            └──────┬───────┘
                   │
      ┌────────────┴────────────┐
      ▼                         ▼
┌───────────┐  handoff   ┌─────────────┐
│   Chat    │ ─────────► │   Coding    │
│ assistant │   prompt   │    agent    │
└─────┬─────┘            └──────┬──────┘
      │ reads                   │ reads STATE at start
      │ (writes, at level 3)    │ writes back at end
      ▼                         ▼
   ┌──────────────────────────────────┐
   │        this repo (the brain)     │
   │  STATE · DECISIONS · BRIEF · ... │
   └──────────────────────────────────┘
```

## The seven files

Every project is a top-level folder holding these:

| File | Answers | Changes |
|------|---------|---------|
| `STATE.md` | What's true right now? | Every session |
| `DECISIONS.md` | Why is it this way? | When a real choice is made (add-only) |
| `BRIEF.md` | What is this and what does done mean? | Rarely |
| `BACKLOG.md` | What's next? | Often |
| `STACK.md` | What tools, services and accounts are in play? | On change |
| `ARCHITECTURE.md` | How does it fit together? | On change |
| `RUNBOOK.md` | How do we keep it running, tech and business? | On change |

Each project also has three folders:

- `prompts/` holds reusable prompts and handoffs for this project.
- `outputs/` holds dated, one-off artefacts: session tails, audits,
  drafts.
- `specs/` holds long documents with version numbers
  (`<topic>-v<n>.md`).

You don't need all seven on day one. STATE, BRIEF, BACKLOG and
DECISIONS do most of the work. STACK, ARCHITECTURE and RUNBOOK earn
their place once there's tech or recurring ops. Leave them as
`_To be populated_` until then.

Shape templates live in [`_global/templates/`](./_global/templates/).
A fully filled-in example lives in [`plant-swap/`](./plant-swap/).

## Get started

1. Click **Use this template** on GitHub. **Make the new repo
   private**, because it's about to hold your real work.
2. Fill in [`_global/PROFILE.md`](./_global/PROFILE.md): who you
   are and how you like to work. Every session reads it.
3. Read through [`plant-swap/`](./plant-swap/), a fictional
   project, to see what good looks like.
4. Pick a setup level (below) and follow its guide.
5. Create your first project with
   [`_global/prompts/new-project.md`](./_global/prompts/new-project.md).
6. Delete `plant-swap/` once it's no longer useful.

## Setup levels

Start at level 1. Move up when the copy-paste starts to annoy you.

| Level | What you get | Needs | Guide |
|-------|--------------|-------|-------|
| **1. Chat only** | Chat reads the brain. You commit what it writes. | A chat app with projects, a GitHub account | [docs/level-1-chat.md](./docs/level-1-chat.md) |
| **2. Chat + agent** | An agent reads and writes the brain directly, and commits. | A coding agent (Claude Code etc.) | [docs/level-2-agent.md](./docs/level-2-agent.md) |
| **3. Shared write** | Chat writes too, so all three actors are live on one repo. | An MCP connector to the repo | [docs/level-3-shared.md](./docs/level-3-shared.md) |

## The session loop

```
start   →  read PROFILE + the project's STATE (+ STACK if it's tech work)
work    →  do the thing
end     →  write the tail block to outputs/
           update STATE (snapshot, not diary)
           add to DECISIONS if something was decided
           move BACKLOG items
next    →  the "Next prompt" from the tail starts the next session
```

The **Next prompt** is the most valuable line in the system. It
lets the next session, whether that's you tomorrow, a fresh chat or
an agent, start in 30 seconds instead of 30 minutes.

## Rules that keep it alive

The full rules are in [`CONVENTIONS.md`](./CONVENTIONS.md), which is
written for an AI to load. The short version:

- **STATE is a snapshot, not a diary.** It has a hard cap. History
  goes to DECISIONS and outputs.
- **Don't fabricate.** `_To be populated_` means ask the human.
- **DECISIONS is add-only.** A reversal is a new entry.
- **The brain is not a database.** Link to live trackers; don't
  copy rows in.
- **No secrets, ever.** Key names only.
- **Small jobs don't get a project.** Put them in a parent's
  `outputs/`.

Why each rule exists: [docs/failure-modes.md](./docs/failure-modes.md).

## Repo layout

```
.
├── README.md              ← you are here
├── CONVENTIONS.md         ← the rules, written for an AI to load
├── CLAUDE.md, AGENTS.md   ← loaders that point agents at CONVENTIONS
├── _global/
│   ├── PROFILE.md         ← who you are, how you work
│   ├── DECISIONS.md       ← decisions about the system itself
│   ├── templates/         ← shapes for the seven files
│   └── prompts/           ← session start/end, handoff, new project, health check
├── docs/                  ← setup guides + failure modes
└── plant-swap/            ← worked example; delete when done
```

## FAQ

**Why not just Google Drive, Notion or a big docs folder?**
Storage isn't the problem. You can keep this repo anywhere you
like. What matters is the fixed shape, the small STATE file and the
write-back habit. Git adds free history and diffs, which matter
once an AI is editing your notes.

**Why not RAG or a vector database?**
Retrieval guesses what's relevant. Here you *know* what's relevant:
STATE first, then whatever STATE points to. At the scale of a
person or small team's projects, a known path beats a search.

**Is it only for code?**
No. RUNBOOK covers business cadence as well as tech ops, and a
project can be a client engagement, a side business or a house
renovation.

**Does it only work with Claude?**
No. It's markdown and git. Any assistant that can read files and
follow instructions can use it. `CLAUDE.md` and `AGENTS.md` are
loaders for the agents that look for those names.

**How many projects before it gets unwieldy?**
The shape scales to dozens of projects. The risk is bloat inside
projects, not the number of them. See the health-check prompt.

## Licence

MIT. See [LICENSE](./LICENSE).
