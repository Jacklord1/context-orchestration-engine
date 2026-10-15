# Failure modes

Every rule in `CONVENTIONS.md` exists because something broke
without anyone noticing. This page lists what breaks, what it looks
like, and the rule that prevents it.

A brain rarely fails loudly. It goes stale gradually until you stop
trusting it, and an untrusted brain is just a folder.

## 1. STATE turns into a diary

**Looks like:** STATE.md is 1,500 lines. Every session added "what
we did" and nobody took anything out. Loading context now costs
thousands of tokens, and today's truth is buried under last
month's.

**Rule:** STATE is a snapshot with a hard cap of 800 tokens. Each
session *overwrites* it. History goes to DECISIONS (the why) and
`outputs/` (the what happened). The health check flags anything
over the cap.

## 2. Updated is mistaken for verified

**Looks like:** STATE was rewritten yesterday, so it feels current.
But it still says the site runs on the old host, because every
session carried that line forward without checking it.

**Rule:** STATE has two dates. `_Last verified:_` only moves after
someone checks the claims against reality and lists `outputs/`. A
stale but honest date tells you to go and look.

## 3. The AI fills the gaps

**Looks like:** STACK.md lists a database you never chose. The AI
saw an empty section and wrote something plausible.

**Rule:** `_To be populated_` means ask, never invent. Stubs are
honest. Plausible fiction is worse than nothing, because it gets
believed.

## 4. The brain becomes a database

**Looks like:** a STATE with a 40-row table of customers or tasks.
It was accurate the day it was pasted in, and nothing has updated
it since.

**Rule:** live data stays in its own tool, and STATE links to it.
The brain holds knowledge (state, decisions, briefs), not
operational rows.

## 5. Half-dead project shells

**Looks like:** 30 project folders, 20 of them never opened since
the day they were scaffolded, each with seven stub files. You can't
tell what's active any more.

**Rule:** small jobs go in a parent project's `outputs/`. Ask "Will
I open STATE for this in three months?" Retired projects move to
`_archive/`.

## 6. Decisions get rewritten

**Looks like:** the DECISIONS entry now says you chose Stripe, but
you remember choosing something else, and the reason is gone.

**Rule:** DECISIONS is add-only. A reversal is a new entry that
names the old one. The *path* to a decision is often what future-you
needs.

## 7. The loop doesn't close

**Looks like:** a great session, then the chat window gets closed.
Next time, nothing in the brain shows it happened.

**Rule:** every session that changed something ends with the tail
block. "Wrap up" is the trigger phrase, and the Next prompt is the
point.

## 8. "Verified" that wasn't

**Looks like:** the tail says "tests pass" and "deployed
successfully". Neither was run; the AI wrote what it expected to be
true.

**Rule:** Verified lists only what was observed. Anything unchecked
goes under Open, explicitly. Read the Verified section before you
trust it.

## 9. A secret lands in markdown

**Looks like:** an API key pasted into STACK.md "just for now",
then synced to three places.

**Rule:** key names only, never values. Values live in a password
manager. The health check scans for anything that looks like a
secret and reports the location, never the value.

## 10. The docs about the system drift

**Looks like:** the README tells new sessions to read a folder you
renamed two months ago. Every session wastes its first minute, or
silently follows a dead rule.

**Rule:** when you change how the brain works, change README,
CONVENTIONS and PROFILE in the same commit and log it in
`_global/DECISIONS.md`. The health check looks for paths the docs
mention that no longer exist.

## 11. Two writers, one STATE

**Looks like:** two sessions on the same project. Both read STATE
at 9am. One writes at 10 and the other at 11, and the 10 o'clock
update is gone.

**Rule:** one active session per project. If you must run more,
re-read STATE immediately before overwriting it, and pull first.

## 12. The canon quietly grows

**Looks like:** projects with `NOTES.md`, `TODO.md`, `IDEAS.md`,
`STATUS.md`... Every session invents a new place to put things, so
nobody knows where anything is.

**Rule:** seven files and three folders. A new file type needs a
DECISIONS entry first. A fixed shape is what lets any session find
things without being told.
