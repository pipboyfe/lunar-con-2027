# Lunar Con 2027 site

Single static file: `index.html`, plus a few images. No build step, no dependencies.
Live on Netlify, deployed from this repo — every push to `main` auto-deploys.

## Structure

- **News** (`#news`) — dated update log, newest post first. To post an update,
  add a new `<article class="news-post">` above the current one with its own
  `<div class="news-date">`.
- **Stay** (`#stay`) — host hotel block (SpringHill Suites Chicago Chinatown),
  rate, dates, booking deadline, and the group-rate booking link.
- **Schedule** (`#schedule`) — day cards: Early Bird (Wed 2/10, optional/exclusive,
  styled distinctly) → Day 1 → Day 2 → Day 3 → Final Day (Sun 2/14).
- **Game Library** (`#games`) — chips linking out to each game's BoardGameGeek
  page, each with a themed emoji prefix. Add a game by copying an existing
  `<a class="game-chip">` line — verify the BGG URL before adding, don't guess it.
- **Suggest** (`#suggest`) — "suggest a game or activity" form.
- **RSVP** (`#rsvp`) — attending (yes/tentative/no) + a separate Early Bird
  checkbox, notes/requests field.

## Images

- `chicago_skyline.jpg` — hero background
- `zodiac_ram_small.png` — ram icon in the hero
- `venmo_qr.jpg` — QR code in the Chip In part of the News post

When adding a new image, resize/compress it for web first (originals from
phones or AI image tools tend to be multiple MB) and only commit the
web-sized version.

## Forms

Both forms (`rsvp`, `game-suggestions`) use Netlify Forms (`data-netlify="true"`)
and submit via `fetch` in the inline `<script>` so a custom success message can
replace the form in place, instead of Netlify's default redirect page.
Submissions land under the Netlify dashboard's Forms tab; email notifications
are configured there too (Project configuration → Forms → Form notifications).

## Editing common things

- **Update the RSVP list**: edit the Confirmed/Tentative `<ul>`s in the News
  section's current post.
- **Add a game**: add a `<a class="game-chip" href="...">emoji Name</a>` line
  to the Game Library grid.
- **Post a news update**: add a new dated `<article class="news-post">` above
  the existing one(s).

## Deploy

Connected via Netlify's GitHub integration (no CLI, no local Node/npm needed).
Build command: none. Publish directory: repo root. Push to `main` and it
redeploys automatically.
