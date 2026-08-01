# Solar System Flashcards

A 1,000-card solar system flashcard app — formation, planets, missions, and the physics of it all. Built as an installable, offline-capable web app (PWA) for iPhone.

## Features

- Tap-to-flip flashcards with swipe-to-grade (right = got it, left = still learning)
- Multiple-choice quiz mode
- Spaced repetition (progress saved on-device via `localStorage`)
- Fully offline after first load, via a service worker that caches the app shell

## Deploying

This is a static site — no build step. Deploy the four files in this repo (`index.html`, `manifest.json`, `service-worker.js`, `icon.svg`) as-is to any static host (Vercel, GitHub Pages, Netlify).

## Installing on iPhone

1. Open the deployed URL in Safari once (requires internet this one time).
2. Share → **Add to Home Screen**.
3. From then on, it loads from the on-device cache — no connectivity required.

## Updating

The service worker uses a versioned cache name (`CACHE_NAME` in `service-worker.js`). Bump that string on any deploy where `index.html` changes, so returning visitors pick up the new version instead of a stale cached copy.
