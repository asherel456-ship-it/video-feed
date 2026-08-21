# Video Feed — Setup

## 1. Create the repo
1. Create a new **public** GitHub repository (e.g. `video-feed`).
2. Upload these files/folders to the root of the repo:
   - `index.html`
   - `manifest.json` (starter file — a GitHub Action keeps it updated automatically, see below)
   - `app.webmanifest`
   - `.github/workflows/update-manifest.yml`
   - a `/videos` folder containing your `.mp4` files

## 2. Manifest.json updates itself
The `update-manifest.yml` workflow watches the `/videos` folder. Any time you push new
video files (or delete some), it automatically rewrites `manifest.json` to match what's
actually in the folder and commits that change for you — same pattern as your other app's
`github-actions[bot]` commits. You never hand-edit `manifest.json`.

If you want to trigger it manually without pushing new videos, go to the repo's
**Actions** tab → "Auto-update manifest.json" → **Run workflow**.

## 3. Enable GitHub Pages
1. Go to the repo's **Settings → Pages**.
2. Under "Build and deployment", set **Source: Deploy from a branch**.
3. Branch: `main`, folder: `/ (root)`. Save.
4. GitHub will give you a URL like `https://yourusername.github.io/video-feed/`.
   (Takes 1–2 minutes to go live after the first deploy.)

## 4. Save it to your phone like an app
1. Open the GitHub Pages URL in Safari (iOS) or Chrome (Android).
2. Tap the Share button → **Add to Home Screen**.
3. It'll launch fullscreen, no browser bar, just like a native app.

## Notes
- Videos play in random order; swiping down retraces your history instead of re-shuffling.
- Autoplay starts muted (a browser requirement) — tap once to enable sound.
- Videos are shown at their original aspect ratio, letterboxed if needed — never cropped.
- Since the repo is public, the video files themselves are technically fetchable by anyone
  who has the direct URL. If you want privacy, say the word and I'll add a simple password
  gate to `index.html` like your other app has.
