# Islamic Desk Clock 🕌

A beautiful full-screen Islamic desk clock designed for a **Raspberry Pi 7" display (1280×720)**. Displays live prayer times, weather, Hijri date, next prayer countdown, and a rotating Quranic verse — all in an elegant dark gold theme.

**Live:** https://rayanshahzad.github.io/islamic-clock/

---

## Features

- **Live clock** — updates every second
- **Prayer times** — Fajr, Sunrise, Dhuhr, Asr, Maghrib, Isha via [Aladhan API](https://aladhan.com/prayer-times-api) (Umm Al-Qura method)
- **Active prayer highlight** — current prayer glows gold
- **Next prayer countdown** — minutes until next salah
- **Hijri & Gregorian date** — both shown, fetched from the API
- **Live weather** — temperature and condition via [Open-Meteo](https://open-meteo.com/) (no API key needed)
- **Quranic verse** — rotates every hour through 24 ayat
- **Islamic aesthetic** — dark navy, gold accents, بسم الله ornament, 8-pointed star corners
- **Scale-to-fit** — renders at 1280×720 and scales to any screen size

---

## Location

Configured for **KAUST, Saudi Arabia** (22.3046°N, 39.1044°E). To change, edit these two lines in `index.html`:

```js
const LAT = 22.3046;
const LON = 39.1044;
```

---

## Raspberry Pi Setup

### 1. Update autostart

Edit `~/.config/labwc/autostart` on the Pi:

```bash
nano ~/.config/labwc/autostart
```

Add this single line:

```bash
chromium --kiosk --noerrdialogs --disable-infobars --no-first-run https://rayanshahzad.github.io/islamic-clock/ &
```

### 2. Reboot

```bash
sudo reboot
```

The Pi will boot directly into the clock. No local server needed — the page loads straight from GitHub Pages.

### To exit kiosk mode

Press `Alt + F4` or SSH in and run:

```bash
pkill chromium
```

---

## Updating the Clock

Edit `index.html` locally, then push:

```bash
git add index.html
git commit -m "Update clock"
git push
```

GitHub Pages deploys within ~60 seconds. The Pi picks up changes on next reload (`F5` in Chromium or reboot).

---

## APIs Used

| API | Purpose | Key required |
|-----|---------|-------------|
| [Aladhan](https://aladhan.com) | Prayer times + Hijri date | No |
| [Open-Meteo](https://open-meteo.com) | Weather | No |
| [AllOrigins](https://allorigins.win) | CORS proxy for Aladhan | No |

---

## Screenshot

> Dark navy background · gold accents · Islamic geometric ornaments · Playfair Display serif clock

---

*Built for personal use at KAUST. Wallah, may it be of benefit.*
