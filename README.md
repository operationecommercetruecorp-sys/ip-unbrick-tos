# TrueStore iPhone Lock Check – live dashboard

A live web dashboard for the iPhone SimLock / Global Blacklist / Find My checks run on imeicheck.com.

**This repository contains no IMEIs or serial numbers.** The page asks the private Google Sheet's
Apps Script web app for **counts only** (`?action=summary`) and refreshes every 30 seconds.

```
imeicheck.com tab (your Chrome)  ──results──▶  Private Google Sheet (IMEIs, Apps Script)
                                                        │  ?action=summary (counts only)
                                                        ▼
                                          GitHub Pages: index.html (this repo)
```

## What the page shows

- Checking progress: checks complete, not checked yet, total, % done
- SimLock donut: Unlocked = green, anything else = red
- Global Blacklist donut: Clean = green, anything else = red
- Find My iPhone ON rate = ON ÷ all iPhone serials
- A Sheet filter, and a per-sheet table (new tabs in the Google Sheet appear automatically)

## Setup

1. In `index.html`, set `const API = '...'` to your Apps Script Web app URL (ends in `/exec`).
2. Commit and push.
3. **Settings → Pages → Build and deployment → Deploy from a branch → `main` / `(root)` → Save.**
   GitHub shows the site address after a minute or two: `https://<user>.github.io/<repo>/`.

GitHub Pages on a free plan needs a **public** repository. That's fine here because nothing in this repo
is private. The IMEIs, the loop script's token and `Code.gs` stay in the private Google Sheet and your private repo.
