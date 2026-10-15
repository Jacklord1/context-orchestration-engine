# Health check

Run this monthly or quarterly. A brain doesn't fail loudly. It
slowly bloats and goes stale until nobody trusts it, and this
catches that early.

## The prompt

```
Run a health check on my brain repo. Report first; change nothing
until I approve.

For every project folder (skip folders starting with `_`):

1. STATE size: estimate tokens. Flag anything over 800 (the cap)
   and anything over 500 (the target).
2. STATE freshness: report the `_Last verified:_` date. Flag
   anything older than 30 days on an active project.
3. STATE vs outputs/: list outputs/. Flag any project whose STATE
   doesn't point at its newest output.
4. Canon: which of the seven files exist? Which are still all
   `_To be populated_`? Flag missing files and extra file types
   with no DECISIONS entry.
5. Liveness: date of the newest commit touching the folder. Flag
   anything untouched for 90 days as a candidate for _archive/.
6. Secrets: flag anything that looks like a key, token, password
   or private URL. Report the file and line only; never print the
   value.

Then, at the brain level:

7. Do README, CONVENTIONS and PROFILE still describe how things
   actually work? Flag any path, folder or project they mention
   that no longer exists.

Output one table (project, size, verified, canon, last touched,
flags), then a short list of recommended fixes, worst first.
```

## Pruning an oversized STATE

When the check flags a STATE over the cap:

```
Prune {project}/STATE.md to under 500 tokens without losing
information:
- Reasoning and history move to DECISIONS.md, as new entries if
  they aren't logged already.
- Session narratives move to the outputs/ files they came from;
  STATE keeps only the link.
- "Where we are" keeps only what is true today.
Show me the diff before writing.
```

## Why it matters

The brain's authority comes from being right. Each stale line
teaches you to double-check it. Once you're double-checking
everything, it's no longer saving you any time.
