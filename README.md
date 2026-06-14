# My Home — Home Improvement Tracker

A simple app to track home improvement projects with before/after photos, budgets, dates, a timeline, and multiple properties. Built as an installable Progressive Web App (PWA).

## Files in this folder
Keep all of these **together at the root** of your repo/host:
- `index.html` — the app
- `manifest.webmanifest` — app name, colors, icons
- `sw.js` — service worker (offline support)
- `icon-192.png`, `icon-512.png`, `icon-maskable-512.png`, `apple-touch-icon.png` — app icons
- `README.md`, `INSTALL.md` — docs (optional to upload)

## Host it free on GitHub Pages
GitHub Pages serves over HTTPS, which the PWA needs for install + offline. The app uses relative paths, so it works fine under a sub-path like `username.github.io/repo-name/`.

**No git required — upload in the browser:**
1. Create a free account at https://github.com
2. Click **New repository**, name it (e.g. `home-tracker`), set it **Public**, and create it.
   *(Public is required for free Pages. Your project data is NOT exposed — it lives only in each phone's browser, not in the code.)*
3. On the repo page: **Add file → Upload files**, then drag in `index.html`, `manifest.webmanifest`, `sw.js`, and the four `.png` icons. Click **Commit changes**.
4. Go to **Settings → Pages**. Set **Source = Deploy from a branch**, **Branch = main**, folder **/ (root)**, then **Save**.
5. Wait ~1 minute and refresh — your live link appears: `https://yourname.github.io/home-tracker/`

**Important:** all files must sit at the **root** of the repo (not inside a subfolder), or the relative paths won't line up.

## Install on your phone
Open the live `https://…` link on your phone:
- **iPhone (Safari):** Share button → **Add to Home Screen**
- **Android (Chrome):** tap the **Install app** prompt, or ⋮ menu → **Install app**

## Updating the app
When you change the app:
1. Re-upload the changed files to the same repo.
2. Bump the cache version in `sw.js` (`hometracker-v1` → `hometracker-v2`) so installed phones pull the new version instead of the cached one.

## Notes & limits
- Data is stored **on each device** (in the browser). A phone and a computer keep separate data until the app gets a cloud backend.
- Photos are auto-compressed on upload, but browser storage is capped at ~5MB total per device.
- For real **App Store / Google Play** apps, the next step is wrapping this with Capacitor and moving storage to on-device files plus a cloud backend (e.g. Supabase or Firebase) for accounts and cross-device sync.
