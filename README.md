# 💊 Pill Timer

A simple, free medication timer app that runs in any mobile browser — no app store, no account, no ads.

Built for elderly or forgetful users who need to know at a glance whether it's safe to take another painkiller. The entire app is a single HTML file.

**[▶ Open the app](https://jase2026.github.io/pill-timer/)**

---

## What it does

- Tracks **two pills independently** — one per half of the screen
- Shows the **time elapsed since the last dose** in very large text
- Turns **green** when under 4 hours (too soon to take again) and **red** when 4+ hours have passed (safe to take again)
- Shows exactly how long until the next dose is safe
- Lets you record **1 or 2 tablets** per dose
- Remembers the **last dose time even when the app is closed** or the phone restarts
- Pill names are **editable** — tap to rename (e.g. Paracetamol, Ibuprofen)

---

## Screenshots

> *(Dark background, two large sections, green/red elapsed time, big PILL SWALLOWED button)*

---

## Installing on your phone (free, no app store needed)

This is a PWA (Progressive Web App) — it installs directly from the browser and works like a native app.

### Android (Chrome)
1. Open **Chrome** and go to `https://jase2026.github.io/pill-timer/`
2. Tap the **three dots menu ⋮** → **Add to Home screen**
   - On Android 14+: tap **Share** → scroll across and tap **Add to Home screen**
3. Tap **Add** — the app icon appears on your home screen

### iPhone (Safari)
1. Open **Safari** and go to `https://jase2026.github.io/pill-timer/`
2. Tap the **Share button** (box with arrow) at the bottom
3. Tap **Add to Home Screen** → **Add**

Once installed, it opens full screen with no browser bar — just like a native app.

---

## Who it's for

Anyone who takes regular medication and needs a simple way to avoid accidental double-dosing. Designed specifically with older users in mind:

- Very large text
- Dark background (easy on the eyes)
- No menus, no settings, no login — just two big buttons
- Works on old Android phones (Android 8+) and any iPhone

---

## Self-hosting / forking

You're welcome to fork this project and host your own version. Everything is in a single file (`index.html`) with no dependencies, no build step, and no backend.

### Files

| File | Purpose |
|------|---------|
| `index.html` | The entire app — HTML, CSS, and JavaScript in one file |
| `manifest.json` | PWA metadata (name, icon, display mode) |
| `sw.js` | Service worker — enables offline use and the install prompt |
| `icon.png` | Home screen icon |

### How to customise

- **Change the 4-hour window** — find `const SAFE_MS = 4 * 60 * 60 * 1000` in `index.html` and change `4` to however many hours you need
- **Change the default pill names** — find `value="Paracetamol"` and `value="Ibuprofen"` in the HTML and update them
- **Change from 2 pills to 1** — remove the second `.pill-section` block and the `.divider`

### Hosting for free with GitHub Pages

1. Fork this repository
2. Go to **Settings → Pages**
3. Set the source branch to **main**
4. Your app will be live at `https://yourusername.github.io/pill-timer/`

---

## Technical notes

- Vanilla JavaScript — no frameworks, no build step
- Timestamps stored in `localStorage` (survives app close and phone restart)
- Timer refreshes every 30 seconds
- Works fully offline once installed (via service worker cache)
- `localStorage` keys: `pillTs1`, `pillTs2` (epoch ms), `pillName1`, `pillName2`, `pillDose1`, `pillDose2`

---

## Possible future improvements

- [ ] Alarm / notification after 4 hours
- [ ] Dose history log
- [ ] Support for more than two pills
- [ ] Configurable dose interval (not just 4 hours)
- [ ] Max doses per day counter

Pull requests welcome!

---

## Licence

MIT — free to use, modify, and share.
