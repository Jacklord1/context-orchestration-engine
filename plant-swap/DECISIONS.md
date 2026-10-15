# Plant Swap — DECISIONS

Newest at the top. Add-only.

## 2026-02-10 — RSVP via a form into a Google Sheet, not a database

We need RSVPs so the library gets a headcount. The options were a
Netlify form, a hosted form tool, or a small database behind a
serverless function.

**Why:** both organisers already live in Google Sheets. A database
adds something to maintain for about 30 rows a month. Netlify Forms
plus a Zapier-free sheet sync (Apps Script) costs nothing.

**Implications:**
- The Sheet is the source of truth for RSVPs. STATE links to it
  and never copies names in.
- Netlify Forms' free tier allows 100 submissions a month, which is
  enough until the swap is three times its current size.
- If we ever need reminders by email, revisit this.

## 2026-01-20 — No user accounts, ever

Someone suggested logins so people could manage their own listings.

**Why:** accounts mean passwords, resets, privacy obligations and
spam, all for a monthly swap of cuttings. Trust is handled at the
table on the day.

**Implications:**
- Listings are submitted through a form and moderated by an
  organiser.
- Rules out any "my swaps" features. Revisit only if the swap
  outgrows one room.

## 2026-01-12 — Static site on Netlify free tier

**Why:** no server to patch, free, and either organiser can edit
markdown on GitHub to update the page.

**Implications:**
- Anything dynamic has to be a form or an embed.
- The site source lives in its own repo (see STACK).

## 2026-01-08 — Started this project

**Why:** the swap has run twice on word of mouth and a group chat.
Both times people turned up to an unbooked room. We need one place
for dates, rules and RSVPs.

**Implications:**
- A brain project for the swap, with the website as its first job.
