# Session end — the tail block

Every session that changed anything ends with write-back. Without
it the loop doesn't close, and the next session starts blank.

## The prompt

```
We're wrapping up. Do the session-end write-back per CONVENTIONS.md:

1. Write the tail block (shape below) to
   {project}/outputs/{YYYY-MM-DD}-{slug}.md
2. Overwrite {project}/STATE.md with an updated snapshot. Keep
   "What this is" word for word. Point "Last session outcome" at
   the tail. Stay under the 800-token cap; prune if needed.
3. If we made a real decision, add an entry to the top of
   {project}/DECISIONS.md.
4. Move finished BACKLOG items to a dated Done section.

If you can't write files, output each one in full so I can commit
it.
```

## Tail block shape

```markdown
# {What was attempted}

One short paragraph: what was asked and what the goal was.

## Result
- What landed. Be specific: file paths, URLs, names.
- What didn't land, said plainly.

## Verified
- Checks actually run, with their actual results.
- Only what was observed, not what was assumed.

## Open
- Loose ends, oddities, things skipped and why.
- Decisions the owner still needs to make.

## Next prompt
> One self-contained paragraph the next session can paste and run.
> Name files and commands explicitly. Don't write "the thing we
> discussed".
```

## Rules of thumb

- **Result is what landed, not what was tried.** Failed attempts go
  under Open.
- **Verified is what was observed.** "Tests pass" only counts if
  they were run. If you couldn't check something, say so.
- **An empty Open is a warning sign.** Every real session turns up
  at least one loose end.
- **The Next prompt has to stand on its own.** A session with no
  memory of this one should be able to paste it and go.
