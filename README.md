# Halo: GOL's Program Cycle Manager

Single-file web app (`index.html`) that mirrors the GOL triage workbook: request normalization,
competition detection, equity-based approvals, secondary offers, day rate pass, budget tracking,
and the communication centre.

## Run locally
Open `index.html` in a browser. No build step.

## Deploy
Push to `main`; the Pages workflow publishes the repo root. Enable it once under
Settings → Pages → Source: **GitHub Actions**.

## Data
State autosaves to the browser's `localStorage` (per browser, per device, per URL).
It does not sync between devices. Clearing site data clears it.

## Updating
Edit `index.html`, commit, push. Reference data (unit/vendor contacts, vendor map, equity targets)
is embedded in the file and must be updated there when the workbook changes.

## v2 additions
- **Sample data only.** Contacts, links and vendor contact names are fake. Real unit/vendor emails are imported per device (Settings → User Profile → Contacts import, CSV `Kind,Name,Email`) and stay in that browser's localStorage.
- **User Profile** (first-run name prompt; device-stamped actions), vendor owner tags, budget flag thresholds.
- **Mid-Cycle Actions**: modify (series-level), swap, cancel, add; pending → proposed → committed/rejected; undo via reversal; unique ActionIDs; lookup with one-tap emails; weekly commitments vs remaining budget; CSV export/import; cycle lock.
- **PWA**: `manifest.webmanifest` + `sw.js` for home-screen install and offline use.
- One-off date moves are handled in Outlook, not in the app.
