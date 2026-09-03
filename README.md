# Lunar Con 2027 site — phase 3 skeleton

Single static file: `index.html`. No build step, no dependencies.

## Deploy to Netlify (fastest)
1. Go to app.netlify.com → "Add new site" → "Deploy manually"
2. Drag the folder containing `index.html` onto the drop zone
3. Done — Netlify auto-detects the two forms (`rsvp` and `game-suggestions`)
   because of the `data-netlify="true"` attribute. Submissions show up
   under Site settings → Forms once the site is live (forms only work
   on a real deploy, not a local preview).

## Deploy via GitHub (better for ongoing edits)
1. Push this folder to a GitHub repo
2. In Netlify: "Add new site" → "Import from Git" → pick the repo
3. Build command: none. Publish directory: `/` (root)

## What's here
- Hero with placeholder dates/location
- Tentative schedule grid (4 day-cards, all TBD — fill in once locked)
- Game library (static list — add games by editing the `.game-grid` block)
- "Suggest a game" form → Netlify Forms
- RSVP form (name, plus-ones, attending y/n, date block preference,
  dietary notes) → Netlify Forms

## Not built yet (later phases)
- Live headcount/tally display (would need to read Netlify Forms
  submissions back into the page — needs a small serverless function)
- Weather + shuttle "brain" automation
- Real content for schedule/games once dates and library are finalized
