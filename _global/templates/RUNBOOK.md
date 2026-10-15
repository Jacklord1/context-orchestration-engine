# RUNBOOK.md template

How to keep the project running. It covers both **tech ops**
(deploy, restore, recover) and **business cadence** (the weekly,
monthly and quarterly rhythms). Both halves count equally.

## Template

```markdown
# {Project} — RUNBOOK

## 1. Tech ops
### Deploy
{How a change reaches production. The actual commands.}

### Restart / restore
{How to bring each part back. Where the logs are. What "healthy"
looks like.}

### Backups
{What's backed up, where, and the date of the last test restore.}

## 2. Business cadence

| Cadence | What | Owner | Notes |
|---------|------|-------|-------|
| Weekly | {e.g. reply to enquiries} | {who} | {…} |
| Monthly | {e.g. send newsletter} | {who} | {…} |
| Quarterly | {e.g. brain health check} | {who} | `_global/prompts/health-check.md` |

## 3. Incident playbooks
### {e.g. "Site is down"}
1. {First check}
2. {Second check}
3. {Who to tell}

## 4. Common procedures
### {e.g. "Onboard a new volunteer"}
1. {Step}
2. {Step}
```

## How to use it

- **Concrete beats vague.** "Run `npm run deploy`" beats "deploy
  the site".
- **Untested procedures are theatre.** A backup you've never
  restored from is a hope, not a backup.
- **Link, don't paste.** Scripts live in code repos, and the
  RUNBOOK names them.

## What goes here and what goes elsewhere

- **RUNBOOK:** repeatable work with an owner and a rhythm.
- **BACKLOG:** "set up backups" stays there until it's done; once
  done, the procedure moves here.
- **outputs/:** what a procedure produced on a given day.
