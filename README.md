# Joe's Practice Map

Live: https://teleokinetic.github.io/joe-practice/ — B "Today first" skin (2026-08-22), prototype artifact is the copy-editing surface; port edits here via `joe-src.html`.

Single-file PWA for Joe's Personal Training for Meditators client dashboard. Mirrors the structure of `max-practice` (manifest + service worker + icons + `audio/`).

**Deploy:** GitHub Pages from the `main` branch, root folder. Everything is relative-path, so it works at any subpath.

**Do not hand-edit `index.html`.** It is generated from `joe-src.html` via `wrap.py` — edit the source and re-run `python3 wrap.py`.

**Offline:** `sw.js` precaches the shell (cache name `joe-map-v2`) and caches the MP3s listed in its `AUDIO` array best-effort with Range support. `copy.json` is never served from cache.

**Audio:** `audio/emotional-inquiry.mp3` (Joe Hudson, Art of Accomplishment — free at view.life/ei) is this week's practice. Tanner's own pain-practice recordings replace/join it later: drop the file in `audio/`, point the player at it in `joe-src.html`, add it to `AUDIO` in `sw.js`, bump the cache name, re-run `wrap.py`.

**Icon:** `icon.svg` is the source (rolling hills + a point in the sky — the Practice Map template mark). Recolour per client, then regenerate `icon-512.png` (master), `icon-maskable-512.png` (same art; safe zone holds), `icon-192.png`, `apple-touch-icon.png` (180).
