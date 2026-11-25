BOUNDARY LIVE — VILLAGE SPORTS BROADCAST
=========================================

WHAT'S INCLUDED
- index.html: complete responsive app, CSS and JavaScript bundled locally
- manifest.json: installable PWA metadata
- sw.js: offline application shell cache
- LocalStorage persistence for match, players and tournament standings
- Ball-by-ball cricket scorer, undo, innings transition, commentary, scorecard, charts
- Player directory with optional local photo storage
- Basic village tournament points table
- Basic multi-sport scoreboards
- Optional Firebase Realtime Database REST publish/watch

RUN LOCALLY
1. Extract the ZIP.
2. For basic testing, open index.html in a modern browser.
3. For PWA installation and service worker support, serve the folder over HTTPS
   or localhost. Example: `python -m http.server 8000`, then visit
   http://localhost:8000

GITHUB PAGES
1. Create a GitHub repository.
2. Upload index.html, manifest.json and sw.js to the repository root.
3. Enable GitHub Pages in repository Settings > Pages.
4. Open the published HTTPS URL. Use "Add to Home Screen" on mobile.

OFFLINE / DATA
- Match and player data are stored in this browser's LocalStorage.
- Keep using the same browser/profile to access local data.
- Clearing browser storage or uninstalling the browser can erase local data.
- Offline scoring works after the app shell has been cached once.
- A service worker cannot be installed from file://; use localhost or HTTPS.
- Photos are stored as base64 in LocalStorage; use modest image sizes.

FIREBASE LIVE SYNC
1. Create a Firebase project and Realtime Database.
2. Copy the database URL, e.g. https://YOUR-PROJECT-default-rtdb.firebaseio.com
3. In Firebase Realtime Database Rules, configure read/write permissions.
   For a quick private test only, rules can be temporarily open; do NOT use
   public read/write rules for a production tournament.
4. Open Watch / Sync, paste the database URL and Match ID.
5. Scorer: Publish current score. Spectators: enter same URL and ID, then Watch.
6. This starter connector uses Firebase REST writes and 2.5-second polling.
   It is near-real-time, not zero-delay. Add Firebase Authentication, per-match
   permissions, server-side validation and abuse protection before public launch.

IMPORTANT LIMITATIONS
- This is a complete runnable offline-first starter/PWA, not a certified
  enterprise production system. No software can honestly guarantee zero bugs,
  zero lag or zero-delay internet delivery across all devices/networks.
- Tournament module currently tracks wins/losses/points. NRR requires reliable
  innings totals and overs faced/conceded; this starter does not fabricate NRR.
- Multi-sport modules provide a generic point scoreboard. Sport-specific match
  clocks, sets, raids, rotations, fouls and rules are not implemented here.
- Career totals are profile fields; match events are not yet automatically
  aggregated into historical player careers.
- Test scoring rules with your local tournament rules before official use.
