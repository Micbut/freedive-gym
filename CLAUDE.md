# Freedive Gym

## Project overview
Freedive training app (O2 & CO2 apnea tables, static apnea timer, breathing exercises). Ships as a PWA and a Tauri v2 desktop app.

## Architecture
- **Single-page app**: all UI lives in `index.html` (vanilla HTML/CSS/JS, no framework)
- **PWA**: `sw.js` (service worker) + `manifest.json` for offline/installable support
- **Tauri v2**: wraps the same frontend for desktop builds (`src-tauri/`)
- **Build output**: Tauri reads from `dist/` (just a copy of `index.html`)

## Commands
- `npm run tauri:dev` — run Tauri dev mode (hot-reload desktop window)
- `npm run tauri:build` — build Tauri desktop app

## Key details
- No build step for the frontend — edit `index.html` directly
- Service worker cache version is in `sw.js` (`CACHE = 'freedive-gym-vN'`); bump it when updating assets
- Tauri config: `src-tauri/tauri.conf.json` (identifier: `com.freedivegym.desktop`)
- Dark theme throughout (background `#0f172a`, accent `#38bdf8`)
