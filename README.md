# Joe's Practice Map

Live: https://teleokinetic.github.io/joe-practice/ — B "Today first" skin (2026-08-22), prototype artifact is the copy-editing surface; port edits here via `joe-src.html`.

Single-file PWA for Joe's Personal Training for Meditators client dashboard. Mirrors the structure of `max-practice` (manifest + service worker + icons + `audio/`).

**Deploy:** GitHub Pages from the `main` branch, root folder. Everything is relative-path, so it works at any subpath.

**Do not hand-edit `index.html`.** It is generated from `joe-src.html` via `wrap.py` — edit the source and re-run `python3 wrap.py`.

**Offline:** `sw.js` precaches the shell (cache name `joe-map-v6`) and caches the MP3s listed in its `AUDIO` array best-effort with Range support. `copy.json` is never served from cache.

**Audio:** `audio/emotional-inquiry.mp3` (Joe Hudson, Art of Accomplishment — free at view.life/ei — with Tanner's Joe-specific cut-ins, 13:24) is the pain-screen practice. `audio/jaw-tongue-pelvis.mp3` (Tanner's 2026-09-10 session lesson, 33:08, mono 96 kbps ≈ −18 LUFS; master + transcript in `Teaching & Movement Content/Practice Audio/`) lives in the Library → lesson screen with a liner-notes block. To add a recording: drop the MP3 in `audio/`, add a Library row + lesson screen in `joe-src.html` and bind it with `bindPlayer(prefix, …)`, add it to `AUDIO` in `sw.js`, bump the cache name, re-run `wrap.py`.

**Icon:** `icon.svg` is the source (rolling hills + a point in the sky — the Practice Map template mark). Recolour per client, then regenerate `icon-512.png` (master), `icon-maskable-512.png` (same art; safe zone holds), `icon-192.png`, `apple-touch-icon.png` (180).
