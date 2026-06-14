# My Home — Installing as a Phone App (PWA)

Your app is now a **Progressive Web App**: once it's online, you can install it on an iPhone or Android phone and it behaves like a downloaded app — its own icon, full screen, and works offline.

## What's in this folder
- `index.html` — the app
- `manifest.webmanifest` — app name, icon, colors
- `sw.js` — service worker (enables offline use)
- `icon-192.png`, `icon-512.png`, `icon-maskable-512.png`, `apple-touch-icon.png` — app icons

Keep all of these files **together in the same folder** — the app references them by relative path.

## Important: it must be hosted online (HTTPS)
Install + offline features only work when the app is served from a secure web address (`https://…`). Opening `index.html` directly from your computer (a `file://` path) still runs the app, but the phone "install" and offline features won't activate. So you need to put this folder on a free static host.

### Easiest free options
1. **Netlify Drop** — go to https://app.netlify.com/drop and drag this whole folder onto the page. You'll instantly get an `https://…netlify.app` link. (Free account lets you keep it.)
2. **Cloudflare Pages** or **GitHub Pages** — also free; better if you want a custom name or version control.

After hosting, open the `https://…` link on your phone.

## Install on iPhone (iOS)
1. Open the link in **Safari** (must be Safari).
2. Tap the **Share** button (square with an up-arrow).
3. Scroll down and tap **Add to Home Screen** → **Add**.
4. The "My Home" icon appears on your home screen.

## Install on Android
1. Open the link in **Chrome**.
2. You'll usually see an **Install app** prompt — tap it. (Or tap the **⋮** menu → **Install app / Add to Home screen**.)
3. The "My Home" icon appears in your app drawer.

## Good to know
- Your projects are stored **on each device** (in the browser). A phone install and your computer keep separate data until the app gets a cloud backend.
- To publish a new version, re-upload the folder to the same host. The service worker version (`hometracker-v1` in `sw.js`) can be bumped to force phones to refresh the cache.
- This PWA route is the quick way to use it on your phone. For real **App Store / Google Play** listings, the next step is wrapping it with Capacitor and moving storage to on-device files + a cloud backend.
