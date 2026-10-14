# Econ Quest

A gamified tracker for the NPTEL **Principles of Economics** (IIT Madras) YouTube playlist: 47 lectures, one a day.

## Features
- Coin checkbox and completion date for every lecture, with a direct YouTube link and the video length
- A stopwatch for each lecture. Only one runs at a time, and it auto-stops after 2 hours
- XP, 10 economics-themed levels, daily streaks, 14 badges, confetti and a level-up screen
- A chart of your progress against the one-a-day plan
- Settings for your name, courses (add more subjects later), lecture lists, and backup/restore
- A daily email reminder, generated as a Google Apps Script that runs from your own Google account

## Files
| File | What it is |
|---|---|
| `index.html` | The full app in one file. Open it in a browser or host it on GitHub Pages. |
| `artifact-source.html` | The same app without the `<html>/<head>` wrapper, the form Claude artifacts are published in. Edit this one if you republish to Claude. |

## Where your data lives
- **On Claude (claude.ai artifact):** progress syncs to your Claude account across devices.
- **On GitHub Pages or a local file:** progress is saved in that browser only. To move it, use **Settings → Backup and reset → Copy backup**, then **Restore from text** on the other copy.
- Your reminder email is never saved anywhere except your own browser and the Apps Script you paste into your Google account. It is not in this code.

## Host it on GitHub Pages
1. Create a new **public** repository (for example `econ-quest`) and upload `index.html`, `artifact-source.html` and this README.
2. Go to **Settings → Pages**, set **Source** to *Deploy from a branch*, choose `main` and `/ (root)`, and save.
3. After a minute the site is live at `https://<your-username>.github.io/econ-quest/`.
4. In the app, open **Settings → Daily email reminder** and set **Link to this tracker** to that address, so the emails point to the hosted copy.

## Updating
Edit `index.html` and commit. GitHub Pages redeploys automatically. The lecture list, start date and lecture count can also be changed from the app's Settings without touching code.

## Daily email reminder
In the app: **Settings → Daily email reminder → Generate my reminder script**, then follow the steps shown. In the script, `setup` schedules the daily email and sends a test, `sendTestEmail` sends one now, and `stopReminders` turns it off.
