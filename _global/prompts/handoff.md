# Handoff — chat to agent

The shape of a prompt that a chat assistant writes for a coding
agent. Chat is good at thinking things through; the agent is good at
doing them. The handoff is the contract between the two.

Use it once a planning chat has produced one clear, scoped goal. If
you can't state the goal in one sentence, write two handoffs.

## Shape

Six blocks, in order, 10–30 lines in total. Past 40 lines you've
packed two goals into one handoff.

```
# Agent: {one-line title}

## Context
Read {project}/STATE.md and STACK.md first.
{One sentence on why this is happening now.}

## Goal
{One sentence. An outcome, not an activity.}

## Constraints
- {What not to touch}
- {What to preserve}
- {Use X, not Y — see DECISIONS YYYY-MM-DD}

## Steps
1. {Concrete action with exact paths}
2. {Concrete action}
3. {Concrete action}

## Definition of done
- {A check that proves it worked: a command, a URL, a test name}
- {Another check}

## Write back
Do the session-end write-back per _global/prompts/session-end.md.
Update STATE if {X} changed. Log a DECISIONS entry if {Y} was
decided.
```

## Notes

- **Exact paths beat descriptions.** `site/src/pages/rsvp.astro`
  beats "the RSVP page".
- **"Done" must be checkable.** "It works" isn't a definition of
  done; a named command and its expected result is.
- **Put risky steps in Constraints**, not buried in Steps: anything
  destructive, anything that spends money, anything that publishes.
- **The write-back block is non-negotiable.** It's how the chat
  assistant learns what happened.
- **Save handoffs you'll reuse** in `{project}/prompts/`.
