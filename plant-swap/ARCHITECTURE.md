# Plant Swap — ARCHITECTURE

## 1. Overview
A static Astro site on Netlify. The only dynamic part is the RSVP
form: Netlify Forms captures each submission and posts it to a
webhook, and a Google Apps Script appends it to a Sheet. Nothing
stores personal data except the Sheet and Netlify's form log.

```
visitor → static site → Netlify Forms ─webhook→ Apps Script → Sheet
```

## 2. Data
- **RSVP:** name, email, date, "bringing" (free text), and whether
  they want the newsletter.
- The Sheet holds one tab per swap date.

## 3. Components
### Site
Astro pages in `plant-swap-site/src/pages/`. Swap dates come from
one file, `src/data/swaps.json`, so changing a date is a one-line
edit.

### RSVP sync
An Apps Script bound to the Sheet. If it fails, submissions still
sit in Netlify's form log and can be exported by hand.

## 4. Integrations
- Netlify Forms webhook → Apps Script.
- Buttondown, used manually for newsletters.

## 5. Cross-cutting concerns
- **Auth:** none for visitors. Organisers use shared logins.
- **Backups:** the Sheet has version history; site source is in
  git.
- **Privacy:** names and emails only. The Sheet is shared with the
  two organisers and nobody else.

## 6. Constraints
- Must stay on free tiers (BRIEF).
- No accounts (DECISIONS 2026-01-20).

## 7. Specs
- [specs/swap-rules-v1.md](./specs/swap-rules-v1.md) — what can be
  swapped and how the day runs.
