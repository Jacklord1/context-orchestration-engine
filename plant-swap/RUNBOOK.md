# Plant Swap — RUNBOOK

## 1. Tech ops

### Deploy
Push to `main` on `plant-swap-site`. Netlify builds and deploys
automatically in about a minute. Check the Deploys tab for a green
tick.

### Change a swap date
Edit `src/data/swaps.json` in the site repo and push.

### RSVPs not reaching the Sheet
1. Check Netlify, Forms, `rsvp`. Are the submissions there?
2. If they are, the Apps Script failed. Open the Sheet, then
   Extensions, Apps Script, Executions, and read the error.
3. Stopgap: export the CSV from Netlify and paste it into the tab.

### Backups
The Sheet's version history and git. Last checked: 2026-02-11
(restored an old Sheet version as a test).

## 2. Business cadence

| Cadence | What | Owner | Notes |
|---------|------|-------|-------|
| Monthly, 4 weeks out | Confirm room booking | Sam | Library desk |
| Monthly, 3 weeks out | Send newsletter | Alex | Draft via the brain, owner sends |
| Monthly, 3 days out | Email headcount to library | Sam | From the Sheet tab |
| Monthly, day after | Note turnout and lessons | Alex | `outputs/YYYY-MM-DD-swap-notes.md` |
| Quarterly | Book the next three dates | Sam | |
| Quarterly | Brain health check | Alex | `_global/prompts/health-check.md` |

## 3. Incident playbooks

### Room double-booked on the day
1. Ask the library desk for any free room.
2. If there's none, move to the park pavilion next door (it's
   covered).
3. Put a sign on the library door and send a short newsletter.

## 4. Common procedures

### Onboard a new co-organiser
1. Add them to the shared password manager vault.
2. Share the Sheet with them.
3. Point them at this RUNBOOK and BRIEF.
