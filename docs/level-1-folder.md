# Level 1 — Claude saves the files itself

**You get:** the full seven-file system. At "wrap up", Claude
writes the updated notes straight into a folder on your computer.
There's nothing to copy or paste.
**You need:** the Claude desktop app (Mac or Windows) on a paid
plan (Pro, Max, Team or Enterprise). That's all: no GitHub, no
git, no terminal.
**Setup time:** about 15 minutes.

New words? See [Words you'll see](../README.md#words-youll-see).

## How it works

The Claude desktop app has a **Code** tab. Despite the name, it's
just Claude with permission to open, edit and save files in one
folder you choose. You point it at your brain folder, and it reads
the notes at the start and saves them at the end.

```
you open the folder in Claude  →  Claude reads STATE  →  you work
                                                          │
next session starts here  ◄──  Claude saves the notes  ◄──  "wrap up"
```

## Setup

### 1. Get the files onto your computer

1. Open this template's page on GitHub. You don't need an account
   for this step.
2. Click the green **Code** button, then **Download ZIP**.
3. Find the ZIP in your Downloads and unzip it. On Windows,
   right-click and choose **Extract All**. On a Mac, double-click
   it.
4. You'll get a folder called something like
   `context-orchestration-engine-main`. Rename it to `brain`.
5. **Move it somewhere backed up.** The best place is inside your
   OneDrive, Dropbox, iCloud Drive or Google Drive folder. Those
   keep old versions of every file, which is your safety net if
   Claude ever saves something wrong.

Check: open the `brain` folder. You should see `README.md`,
`CONVENTIONS.md`, `CLAUDE.md`, a `_global` folder and a
`plant-swap` folder directly inside it, not inside another folder.

### 2. Open the folder in Claude

1. Open the Claude desktop app and sign in.
2. Click the **Code** tab at the top.
3. Choose **Local**, click **Select folder**, and pick your `brain`
   folder.

### 3. Your first session

Type:

```
Read CLAUDE.md and CONVENTIONS.md. Then help me fill in
_global/PROFILE.md by asking me the questions one at a time.
```

Claude will ask before it changes any file. You'll see the change
with the old text and new text side by side and buttons to
**Accept** or **Reject** it. Read the first few carefully. That's
how you learn to trust it.

Once you're comfortable, switch the mode selector next to the send
button from **Manual** to **Accept edits**. Claude then saves notes
without asking each time. Stay away from any mode with "bypass" in
the name.

### 4. Your first project

```
Read _global/prompts/new-project.md and follow it.
```

Claude asks five questions and creates the project folder and its
files.

Have a look at `plant-swap/` first if you like; it's a filled-in
example. Delete it when you're done with it.

## Every day

1. Open the Claude app, then **Code → Local**, and pick your
   `brain` folder. Recent folders are remembered.
2. Start with:
   ```
   Read CONVENTIONS.md and kitchen-reno/STATE.md.
   ```
   (Use your project's folder name.) Or paste the **Next prompt**
   from the end of STATE.
3. Work. Plan, draft, decide, whatever the project needs.
4. Say **"wrap up"**. Claude writes the session notes, updates
   STATE, logs decisions and ticks off the to-do list, all saved
   into the folder.
5. Skim what changed. This is where you catch the AI making things
   up.

## Common snags

- **"Claude doesn't seem to know my project."** Make sure you chose
  the `brain` folder itself, not the folder above it, and ask it to
  read STATE explicitly.
- **"The Code tab asks me to upgrade."** The Code tab needs a paid
  plan. Use [level 0](./level-0-notes.md) until then.
- **"Claude saved something wrong."** Ask it to fix the file, or
  restore the previous version from OneDrive or Dropbox version
  history.
- **"It wants to run a command and I don't know what it does."**
  Click Reject and ask it to explain in plain English first. The
  brain only ever needs Claude to read and write text files.

## You can still use normal chat

The Code tab is where notes get saved. For thinking out loud on
your phone, a normal Claude chat is fine. Copy anything worth
keeping into the next Code session and say "add this to
DECISIONS".

## When to move up

Move to [level 2](./level-2-github.md) when you want full history
of every change, your notes on more than one computer, or normal
Claude chats to be able to read your brain too.
