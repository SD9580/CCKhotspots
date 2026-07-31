# CCK Hotspots

Live 48-hour schedule for CCK's food-truck hotspots (Driving Range, Willow Square, 9735 Main, Park Slope, Clarence Car Wash). Rendered as a TV display page and hosted on GitHub Pages.

## How it works

A GitHub Action (`.github/workflows/fetch.yml`) runs `fetch_tfc.py` every 15 minutes. The script fetches the next 7 days of bookings from The Food Corridor's public ganttdata endpoint for the Clarence Creative Kitchen listing, filters to the five hotspot calendars, and writes `events.json` at the repo root. The static `index.html` reads that file client-side and renders the schedule.

## Enable GitHub Pages

Settings → Pages → Source: Deploy from a branch → Branch: `main` / `/(root)` → Save.

## Files

- `index.html` — TV display page (single file, no build step)
- `cck_logo.png` — CCK logo used in the header
- `fetch_tfc.py` — data fetcher (Python 3.11+, stdlib only)
- `.github/workflows/fetch.yml` — scheduled Action
- `events.json` — data file (auto-updated)
