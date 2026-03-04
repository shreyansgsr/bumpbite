# BumpBite — Deployment Guide

## What's in the zip:
```
bumpbite/
  index.html      ← Main app
  manifest.json   ← PWA config (name, icon, theme)
  sw.js           ← Service worker (offline support)
  icons/
    icon-192.png  ← App icon (home screen)
    icon-512.png  ← App icon (splash screen)
```

## Deploy to GitHub Pages (5 minutes)

### Step 1: Create a GitHub repo
- Go to https://github.com/new
- Name it `bumpbite`
- Keep it **Public** (required for free GitHub Pages)
- Click **Create repository**

### Step 2: Upload the files
- On the repo page, click **"uploading an existing file"**
- Drag and drop ALL files from inside the `bumpbite/` folder:
  - `index.html`
  - `manifest.json`
  - `sw.js`
  - `icons/` folder (with both PNGs)
- Click **Commit changes**

> **Important:** Upload the FILES inside `bumpbite/`, not the folder itself.
> The `index.html` should be at the root of the repo, not inside a subfolder.

### Step 3: Enable GitHub Pages
- Go to your repo → **Settings** → **Pages** (left sidebar)
- Under "Source", select **Deploy from a branch**
- Branch: **main**, Folder: **/ (root)**
- Click **Save**
- Wait 1-2 minutes

### Step 4: Access your app
- Your app will be live at: `https://YOUR-USERNAME.github.io/bumpbite/`
- Open this URL on your phone
- You should see a banner saying **"Install BumpBite"** — tap it!
- If no banner, use browser menu → **"Add to Home Screen"**

### Step 5: Share with your wife
- Just WhatsApp her the URL
- She opens it → taps Install / Add to Home Screen
- Done! Both of you have the app.

## Troubleshooting

**"Install" banner doesn't show?**
- Use browser menu (⋮) → "Add to Home Screen" or "Install App"
- On iOS Safari: Share button (□↑) → "Add to Home Screen"

**Changes not showing after update?**
- The service worker caches files. To force update:
  - Increment `CACHE_NAME` in `sw.js` from `bumpbite-v1` to `bumpbite-v2`
  - Re-upload `sw.js` to GitHub

**Data not syncing between phones?**
- By design — each phone stores its own checklist data locally
- This means you and your wife track independently
