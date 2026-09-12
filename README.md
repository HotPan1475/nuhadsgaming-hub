# Gaming Hub

## Structure
```
/index.html                        → hub landing page
/games/cosmic-invaders/index.html  → Cosmic Invaders (self-contained)
/games/<next-game>/index.html      → each future game, self-contained
/shared/                           → reusable JS (sound engine, leaderboard client) — add as games are built
netlify.toml                       → deploy config (publish repo root, no build step)
```

## Updating one game
1. Edit only that game's file, e.g. `games/cosmic-invaders/index.html`.
2. `git add games/cosmic-invaders/index.html && git commit -m "..." && git push`
3. Netlify auto-deploys the new commit. Other games and the landing page are untouched.

## Deploying for the first time
1. Push this folder to a new GitHub repo.
2. In Netlify: "Add new site" → "Import from Git" → pick the repo.
3. Build settings: no build command needed, publish directory = `.` (already set in netlify.toml).
4. Deploy — Netlify gives you a live URL immediately, and redeploys automatically on every push to `main`.

## Rolling back a bad update
Netlify keeps every deploy. If an update breaks a game, go to the site's "Deploys" tab and click "Publish deploy" on the last good one — instant rollback, no code changes needed.
