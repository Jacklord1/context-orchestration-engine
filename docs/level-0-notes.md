# Level 0 — One note per project

**You get:** every chat about a project starts already knowing
where things stand.
**You need:** the Claude or ChatGPT app with Projects. No GitHub,
no files on your computer, no installs.
**Setup time:** 10 minutes.

This is the lightest version of the system. It skips everything
except the part that matters most: a short "where things stand"
note that the AI reads first and that you keep up to date.

New words? See [Words you'll see](../README.md#words-youll-see).

## Setup

1. **Make a Project** in your chat app, one per piece of work, for
   example "Kitchen reno". (In Claude: **Projects → New project**.
   ChatGPT also has Projects.)
2. **Paste these instructions** into the Project's instructions
   box:

   ```
   This Project has a note called STATE in its files. It's the
   short "where things stand" page for this work.

   - Read STATE before answering anything.
   - Never invent details that aren't in STATE or in our chat; ask.
   - If STATE looks out of date compared with what I tell you,
     say so.
   - When I say "wrap up", write a new STATE in exactly this
     shape, under 400 words, replacing the old one:

     # STATE
     Updated: {today's date}
     ## What this is (one paragraph, keep it the same each time)
     ## Where we are (3-5 bullets, only what's true now)
     ## Decided (one line each, with the date, and why if short)
     ## Open (what's waiting or stuck)
     ## Next (the exact message to start the next chat with)
   ```

3. **Make the first STATE.** In a new chat in the Project, say:
   "Ask me five questions about this work, then write the first
   STATE." Save the answer as a file called `STATE.md` and add it
   to the Project's files (in Claude: **Add content → Upload
   files**, or paste it as text content).

## Every day

1. Open a new chat in the Project. Say what you want to do.
2. Work.
3. Say **"wrap up"**.
4. Replace the old STATE in the Project's files with the new one.
   Skim it first. This is where you catch the AI making things up.
5. Next time, paste the **Next** line to start the chat.

## What you give up

- **No history.** If the AI drops something from STATE, it's gone.
  Keeping a copy of each old STATE in a folder is a cheap fix.
- **Projects don't share notes.** Each Project only knows its own
  STATE.
- **You're still copying one file by hand.** It's one file, though,
  not seven.

## When to move up

Move to [level 1](./level-1-folder.md) when replacing the note
starts to feel like a chore, or when you want the AI to keep
decisions and to-dos in their own files instead of squeezing them
into STATE. At level 1 the AI saves the files itself.
