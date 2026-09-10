# Prosthetic Care Notes

An offline-first Progressive Web App for logging prosthetic care observations — comfort levels, exercises, and appointments. Built as part of the SWEP 2026 PWA workshop.

**Live app:** https://paulina01-tech.github.io/offline-noteslab/

## What it does

- Save notes with a title, category (Comfort, Exercise, Appointment, Other), and observation text
- Notes are stored locally in the browser using localStorage
- Works fully offline once loaded, thanks to a service worker caching the app shell
- Installable as a standalone app via the web app manifest
- Shows real-time online/offline status

## Files

- `index.html` — the entire app: markup, styling, and JavaScript logic
- `sw.js` — service worker that caches the app shell for offline use
- `manifest.json` — web app manifest, enables installability

## Run locally

No build tools needed — it's plain HTML/CSS/JS. Just open `index.html` in a browser, or serve the folder with any static server.

## PWA test performed

1. Opened the live GitHub Pages link once while online (service worker registers and caches the shell)
2. Turned on Airplane Mode
3. Reloaded the page — app loaded fully offline, status showed "Offline"
4. Created new notes while offline — saved successfully via localStorage
5. Turned Wi-Fi back on, reloaded — status updated to "Online", notes persisted

## Notes

This app deliberately uses localStorage rather than IndexedDB, since the data is small and simple (a beginner-appropriate choice, per the workshop guide). A natural extension would be to add a delete/search feature, or move to IndexedDB if the note volume grew.
