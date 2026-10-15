# Level 2 — Add GitHub

**You get:** a full history of every change ("what did STATE say
last Tuesday?"), your brain on any computer, and normal Claude
chats able to read it.
**You need:** level 1, plus a free GitHub account. Optionally, the
free GitHub Desktop app.
**Setup time:** about 20 minutes.

New words? See [Words you'll see](../README.md#words-youll-see).

## What changes

At level 1 your notes live in one folder. At level 2 that folder
becomes a **repo**: every save can become a checkpoint with a note
saying what changed, and GitHub keeps an online copy.

You don't need to learn git. Saving a checkpoint is two buttons in
GitHub Desktop, and the Claude Code tab can usually do it for you.

## Setup

Use one of these routes.

### Route A: you already have a level 1 folder (GitHub Desktop)

1. Install **GitHub Desktop** (desktop.github.com) and sign in with
   your GitHub account.
2. **File → Add local repository**, and choose your `brain` folder.
   It will say the folder isn't a repository yet; click **create a
   repository** and confirm.
3. Click **Publish repository**. **Leave "Keep this code private"
   ticked.** Your real notes are going in here.

### Route B: starting fresh

1. Sign in to GitHub, open this template's page, and click **Use
   this template → Create a new repository**. Name it `brain` and
   set it to **Private**.
2. In GitHub Desktop: **File → Clone repository**, pick `brain`,
   and choose where on your computer it goes.
3. Carry on with [level 1](./level-1-folder.md) from step 2, opening
   that folder in the Code tab.

## The daily loop

Same as level 1, plus one step at the end:

1. Open the folder in the Code tab. Work. Say **"wrap up"**.
2. **Save a checkpoint and upload it**, using whichever you prefer:
   - **GitHub Desktop:** it already lists the changed files, with a
     before-and-after view of each. Type a short summary such as
     `kitchen-reno: picked the tiler`, click **Commit to main**,
     then **Push origin**.
   - **Ask Claude:** "commit these changes and push them." Claude
     runs git for you and asks permission first. This needs git
     installed: most Macs have it, and on Windows install **Git for
     Windows** (git-scm.com). If it doesn't work, use GitHub
     Desktop.

Make the habit "wrap up, then commit". One checkpoint per session
is plenty.

## Let normal Claude chats read the brain

1. In Claude: **Projects → New project**, and call it "Brain".
2. Add your GitHub repo to the Project's knowledge (Claude's GitHub
   integration). For a private repo you'll be asked to give the
   Claude GitHub app access.
3. Paste [`_global/prompts/chat-project-instructions.md`](../_global/prompts/chat-project-instructions.md)
   into the Project's instructions.

**This copy doesn't update itself.** It's a snapshot, so press
**Sync** in the Project after you push, or chat will read old
notes. Chat can read the brain but can't save to it; save through
the Code tab.

## The no-install route (if you must)

You can edit files directly on github.com: open a file, click the
pencil icon, paste, and click **Commit changes**. It works for a
quick fix. As a daily routine it's tedious enough that most people
quit, which is why level 1 has Claude save the files.

## On your phone

Claude Code on the web (claude.ai/code) can work on a GitHub repo
from a browser. It makes its changes on a separate **branch** (a
side copy) and you merge them in with a **pull request**. That's
fine for developers and a step too far for most people.

## For developers: connect your code repos

If your projects' code lives in other repos, add this to each code
repo's `CLAUDE.md` or `AGENTS.md`. An agent working on the code
then keeps the brain current too:

```markdown
## Brain
This repo's canon lives at ~/brain/{project}/. At session start
read ~/brain/CONVENTIONS.md and ~/brain/{project}/STATE.md. At
session end, do the write-back from
~/brain/_global/prompts/session-end.md and commit it in the brain
repo (not this one).
```

Plan in chat, hand over with
[`_global/prompts/handoff.md`](../_global/prompts/handoff.md), and
let the agent do the work and the write-back.

## Tips

- **Push after every session.** Chat and your other computers only
  see what's on GitHub.
- **One Claude session per project at a time.** Two sessions
  saving the same STATE will lose one of them.
- **Read the before-and-after view before you commit.** It's the
  fastest way to catch invented content.

## When to move up

Move to [level 3](./level-3-shared.md) when you want a normal chat,
for example on your phone, to save to the brain directly rather
than just read it.
