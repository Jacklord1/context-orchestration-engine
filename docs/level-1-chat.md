# Level 1 — Chat only

**You get:** every chat starts already knowing your projects, and
ends by handing you the updated files.
**You need:** a chat app with "projects" (shared instructions and
files across chats) and a GitHub account. No code, no terminal.
**Setup time:** about 20 minutes.

## How it works

```
chat reads the brain  →  you work together  →  "wrap up"
        ▲                                          │
        │                                          ▼
   re-sync knowledge  ◄──  you commit  ◄──  chat outputs the files
```

At this level chat can read the brain but can't write to it. You
are the write path: chat hands you the files and you commit them.
That sounds like friction, but it's also your review step.

## Setup

1. **Create your private repo** from this template (README, Get
   started, step 1).
2. **Fill in `_global/PROFILE.md`.** You can do this in GitHub's
   web editor: open the file and press the pencil icon.
3. **Create a project in your chat app.** Call it something like
   "Brain".
4. **Give the project the brain.** Use whichever your app supports:
   - **Repo sync:** some chat apps can attach a GitHub repo, or
     selected files from one, as project knowledge. Attach
     `_global/`, `CONVENTIONS.md`, and the folders of your active
     projects.
   - **Upload:** otherwise upload those files by hand. Re-upload
     STATE when it changes.
5. **Paste the instructions.** Copy the block from
   [`_global/prompts/chat-project-instructions.md`](../_global/prompts/chat-project-instructions.md)
   into the project's instructions field, using the level 1
   options.
6. **Scaffold your first project.** In a new chat in that project,
   paste [`_global/prompts/new-project.md`](../_global/prompts/new-project.md).
   It will ask five questions and output the files. Commit them
   (GitHub web: **Add file → Create new file**, with the path
   `my-project/STATE.md` and so on).

## The daily loop

1. Open a chat in the project and say which project you're on.
2. Work.
3. Say **"wrap up"**. Chat outputs the tail block, the new STATE,
   and any DECISIONS or BACKLOG changes.
4. Commit them. Re-sync or re-upload STATE if your app doesn't
   sync automatically.

## Tips

- **Commit the tail even when you're tired.** The Next prompt is
  what makes tomorrow fast.
- **Read the diff before you commit.** At level 1 you're the
  reviewer, and this is where you catch the AI inventing things.
- **Commit messages:** `project: what changed`. You'll want them
  later.

## When to move up

Move to [level 2](./level-2-agent.md) when you use a coding agent,
or when copy-pasting files is the thing stopping you from wrapping
up.
