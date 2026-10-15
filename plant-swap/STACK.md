# Plant Swap — STACK

## Tools and tech

| Layer | Choice | Decided |
|-------|--------|---------|
| Website | Astro static site | 2026-01-12 |
| Hosting | Netlify free tier | 2026-01-12 |
| RSVP | Netlify Forms → Google Sheet | 2026-02-10 |
| Newsletter | Buttondown free tier | 2026-01-14 |

## Services and accounts

| Service | Account | Cost / month | Owner |
|---------|---------|--------------|-------|
| Netlify | the swap's shared login | $0 | Alex |
| Google Sheets | the swap's shared Google account | $0 | Sam |
| Buttondown | the swap's shared login | $0 | Alex |
| Domain | registrar, renews each January | ~$2 | Alex |

## Code repos

- `plant-swap-site` — on GitHub, the Astro site source.

## Secrets used (names only)

Values live in the organisers' shared password manager vault.

- `NETLIFY_FORM_HOOK_URL` — webhook the Apps Script listens on
- `BUTTONDOWN_API_KEY` — for scripted newsletter drafts
