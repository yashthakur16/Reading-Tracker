# Reading Tracker – Single-File Web App

A lightweight, privacy-friendly reading tracker in a single HTML file (index.html). Search books from the web, add them with cover art, track pages with a slider, switch light/dark mode, and optionally use advanced features like sessions, daily goals, streaks, notes, reminders, and CSV backup — all stored locally in the browser.

## Features

- Book search with cover thumbnails (Google Books)
- Add books with total pages; track progress via slider
- Auto-calculated completion percentage
- Light/Dark mode toggle with system preference on first load
- LocalStorage persistence (no backend, no sign-in)

Advanced (included in this single file):
- Reading sessions (start/stop), log +pages, auto pace estimation
- Daily reading goal and streak tracking with progress ring
- Per-book and global stats (time, pages, sessions, avg pace)
- Notes/highlights with optional @page tagging
- Optional daily reminder notification at a chosen time
- Status shelves: To read, Reading, Finished + filter
- CSV export/import (library, sessions, notes)

## Demo

Open index.html locally in a modern browser, or deploy via GitHub Pages for an HTTPS URL.

## Getting Started

1. Download or clone this repository
2. Ensure the file structure:
   - index.html
3. Open index.html in a browser:
   - Double-click the file, or
   - Run a local static server:
     - `npx serve .`
     - `python3 -m http.server 5500`
4. Optional: Add a Google Books API key for higher reliability
   - In index.html, find the Google Books fetch URL and append `&key=YOUR_API_KEY`.
   - Restrict the key to your GitHub Pages domain in Google Cloud Console.

## Deploy on GitHub Pages

1. Create a new public repository (e.g., `reading-tracker`).
2. Upload `index.html` to the repository root.
3. In the repo:
   - Settings → Pages → Build and deployment
   - Source: Deploy from a branch
   - Branch: `main`, Folder: `/` (root)
4. Save and wait 1–2 minutes.
5. Your app will be available at:
   - `https://yashthakur16.github.io/reading-tracker`

Optional: Custom domain
- Add your domain under Pages settings and follow DNS instructions.

## How to Use

- Search: Enter title/author/ISBN and click Search.
- Add: Choose a book, confirm total pages (auto-prefilled when available).
- Track: Drag the slider; the percentage badge updates instantly.
- Sessions: Start to begin a session, log `+pages`, Stop to save time.
- Goals & Streaks: Set a daily minutes goal; the header shows progress and streak.
- Notes: Add note/highlight; include `@123` to reference page 123.
- Shelves: Use status dropdown per book and the filter at the top.
- Reminders: Set a time, enable notifications; reminders fire while the tab is open.
- Backup: Export CSV; later import to restore or merge.

## Privacy and Storage

- All data (library, sessions, notes, settings) is stored locally in the browser’s LocalStorage.
- No external database or account is required.
- Browser notifications are optional and permission-based.

## Browser Support

- Latest Chrome, Edge, Firefox, and Safari.
- Notifications require HTTPS (GitHub Pages provides HTTPS automatically).
- Dark mode respects system preference on first visit.

## File Overview

- `index.html`: Contains markup, styles, and JavaScript — everything in one file.

Main modules inside the script:
- State: settings, library, sessions, notes
- Search: Google Books API integration
- Library: cards with slider, pages input, shelves, actions
- Sessions: start/stop/log with pace estimation
- Goals & Streaks: daily progress ring and streak chip
- Stats: global and per-book summaries
- Notes: add and quick view
- Reminders: optional daily local notification
- CSV: export/import for backup and migration

## Configuration

- Daily goal: Adjustable from the toolbar (default 30min).
- Reminder time: Set `HH:MM`; enable notifications to receive a nudge.
- Accent/theme: Preconfigured light/dark palettes with accessible contrast.

## Common Issues

- Search rate limits: Google Books usually works without a key at low volume. Add `&key=YOUR_API_KEY` to the fetch URL for higher reliability, and restrict the key to your domain.
- Notifications not showing: Ensure HTTPS (GitHub Pages) and allow notifications in the browser. Current implementation only reminds while the tab is open.
- Data missing after redeploy: Data lives in the browser. Use CSV export before clearing site data or switching browsers/devices.

## Roadmap (optional ideas)

- PWA: Add `manifest.json` and a service worker for installable offline support.
- Cloud sync: Optional backend (e.g., Supabase/Firebase) for multi-device sync.
- Enhanced analytics: Reading calendar heatmap and pace trends.
- Accessibility: More ARIA labels and keyboard shortcuts.

## License

MIT 

## Acknowledgements

Google Books API for public book search and cover thumbnails.
