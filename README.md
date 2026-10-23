# GameTracker

Personal web app (PWA) to track video games across PlayStation, PC and Switch:

- **En cours**: progress, objectives, play sessions with notes and duration.
- **Backlog**: games to play next, ordered by priority.
- **Sorties**: release reminders for games and DLC, exportable to the iPhone calendar (.ics with alerts the day before and on release day at 09:00).
- **Terminés**: finished or dropped games.

Data is stored locally on the device (`localStorage`). Use *Réglages → Exporter* regularly to keep a JSON backup.

## Files

| File | Role |
|---|---|
| `index.html` | The whole app (HTML, CSS, JS) |
| `manifest.webmanifest` | PWA metadata (name, icons, standalone display) |
| `sw.js` | Service worker: offline app shell |
| `icon-*.png` | Home-screen icons |

## Deploy (GitHub Pages, free)

A PWA must be served over HTTPS to be installable.

1. Create a new GitHub repository (e.g. `gametracker`).
2. Upload all files from this folder to the repository root.
3. *Settings → Pages → Build and deployment*: source **Deploy from a branch**, branch `main`, folder `/ (root)`.
4. Wait a minute, then open `https://<username>.github.io/gametracker/`.

## Install on iPhone

1. Open the URL in **Safari**.
2. Share button → **Sur l'écran d'accueil** (Add to Home Screen).
3. Launch GameTracker from the home screen.

## RAWG API key

1. Create a free account at https://rawg.io/apidocs and get an API key.
2. In the app: *Réglages → Clé API* → paste → *Enregistrer*.

The key is stored only on the device and sent only to `api.rawg.io`.

## Updating the app

After changing any file, bump `CACHE_NAME` in `sw.js` (e.g. `gametracker-v2`) so installed copies pick up the new version. Close and reopen the app once (sometimes twice).
