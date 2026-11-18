# Study Town — Playable Stable Release v2

Study Town is a separate, browser-based pixel-art-inspired companion to BSA Study Desk. This package contains the complete standalone game. It is meant to be deployed as a **separate GitHub Pages repository** named `study-town`, alongside the existing `dashboard` repository.

## Install

1. Create `study-town` in the same GitHub account as `dashboard`.
2. Upload **all** files: `index.html`, `style.css`, `game.js`, `manifest.json`, and the complete `assets` folder. Keep their relative paths.
3. In repository Settings → Pages, enable deployment from the root of the default branch. URL: `https://ghostbymegumiacorda.github.io/study-town/` (only when published).
4. Keep BSA Study Desk deployed separately; the launcher package is in the accompanying ZIP. Do not erase browser site data.
5. Use Saves → Export Town Save before moving devices, browsers, or reinstalling.

## How to play

- Explore: WASD/arrow keys or touchscreen D-pad. E or Interact to enter nearby locations. Destination cards also provide Visit buttons. Back to Town returns to the square.
- My Home: place/unplace furniture.
- Avatar: choose poses, colors, outfit, hairstyle silhouettes, and accessories. The appearance changes are rendered on canvas, using the supplied pixel sprite images.
- Pets: buy pets and food at Market, select a companion, feed it, and revive after prolonged hunger. Pet feeding state persists by animal.
- Market: Town Tickets from eligible academic XP, separate from existing Study Coins.
- Journal: quests, friends, collectibles and milestones.
- Saves: import/export a local town save; import dashboard backup for academic XP.

## Academic integration & privacy

- The game's academic XP key `bsa-academic-progress-v1` is **read-only**. Town data is stored separately in browser storage under `bsa-study-town-save-v1`.
- Both GitHub Pages sites under `ghostbymegumiacorda.github.io` normally share one browser origin, so the game can read the academic XP ledger on the same device. Cloud synchronization between devices is **not** implemented.
- Tickets are local-only and not fraud-resistant. A verified cloud economy would need authentication and server-side accounting. Games and town activities award no academic XP.
- Existing dashboard subjects, study-time totals, quizzes, academic rank, Study Coins, and pets in the dashboard are not modified by the game.

## Tests and limits

Read `TEST-REPORT.md` for verified checks. Chromium-based desktop and phone viewport tests loaded bundled HTML/CSS/JS in an isolated test page because direct local file/http browser navigation is restricted in this environment.

This is a **stable playable starter game**, not a finished large-scale life simulator: there are seven simplified visitable town locations and working starter activities, but no seamless multi-map exploration, moving NPCs, full handcrafted tile sets, multiplayer, cloud sync, or hand-drawn sprite variants for every avatar choice. Different avatar settings are approximate color edits and simple silhouette/accessory changes, not new fully illustrated sprites.
