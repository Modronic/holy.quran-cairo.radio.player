# 🌙 Holy Quran Radio PLayer — Cairo Quran Radio, Live

**Live from Cairo, Egypt · Currently streaming "Idha'at Al-Quran Al-Karim"**

![Status](https://img.shields.io/badge/status-live-brightgreen?style=for-the-badge)
![Version](https://img.shields.io/badge/version-1.0-gold?style=for-the-badge)
![License](https://img.shields.io/badge/license-MIT-blue?style=for-the-badge)
![Zero Dependencies](https://img.shields.io/badge/dependencies-zero-purple?style=for-the-badge)

A beautiful, minimalist web application for listening to the Holy Quran in radio style, streaming live from Cairo. Built with pure HTML, CSS, and JavaScript — **zero dependencies**, **single HTML file**, **respectful design**.

بِسْمِ اللَّهِ الرَّحْمَٰنِ الرَّحِيمِ
> "وَإِذَا قُرِئَ الْقُرْآنُ فَاسْتَمِعُوا لَهُ وَأَنْصِتُوا لَعَلَّكُمْ تُرْحَمُونَ"
> — سورة الأعراف، الآية ٢٠٤

[🎧 Live Demo](https://modronic.github.io/Quran-Radio/) · [📱 Install on Home Screen](#-pwa--home-screen-installation)

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| **Pure Vanilla** | Zero frameworks, zero dependencies — single HTML file |
| **Beautiful UI** | Sacred ۞ symbol with breathing animations, glassmorphism design |
| **Smart Streams** | Primary CDN + 3 backup nodes with automatic failover |
| **Prayer Times** | Live Cairo prayer countdown via Al-Adhan API with Hijri date |
| **Sleep Timer** | Auto-stop at 20, 30, 45, or 90 minutes |
| **Universal Share** | 4-tier share system — works on every device ever made |
| **PWA Ready** | Install on home screen for native-like background playback |
| **Media Session** | Lock screen controls, artwork, and play/pause on all platforms |
| **Volume Memory** | Saves your volume preference across sessions |
| **Emergency Refresh** | Full cache + service worker nuke with one tap |
| **Adblock Detection** | Friendly notice if stream-blocking is detected |
| **Console Clean** | Zero errors or warnings in production |
| **Lightweight** | Single file — loads in under 1 second on any connection |

---

## 📡 Stream Architecture

The app connects to **Cairo Quran Radio** (إذاعة القرآن الكريم) through four redundant nodes. If the primary CDN fails, the app silently tries the next — no interruption, no manual action needed.

```
Primary  → stream.radiojar.com/8s5u5tpdtwzuv   (CDN)
Backup 1 → n03.radiojar.com/8s5u5tpdtwzuv
Backup 2 → n04.radiojar.com/8s5u5tpdtwzuv
Backup 3 → n0e.radiojar.com/8s5u5tpdtwzuv
```

---

## 🔗 Universal Share System

The share button uses a **4-tier waterfall** — it always finds a method that works, no matter what device or browser is being used:

| Tier | Method | Covers |
|------|--------|--------|
| **1** | `navigator.share` — Native OS share sheet | Windows 10/11, macOS, Android, iOS, Samsung Internet, modern smart TVs |
| **2** | `navigator.clipboard.writeText` | Firefox desktop, Linux, any HTTPS browser without share API |
| **3** | `document.execCommand('copy')` via hidden textarea | iOS Safari 10–13, Android Chrome 43–65, old Samsung Internet |
| **4** | In-page URL overlay | WebViews, in-app browsers (Facebook, Instagram, etc.), smartwatches, anything else |

Tier 4 shows a copyable URL bar directly inside the app — no popups, no permissions, zero browser restrictions.

---

## ❔ How to Use

### For Listeners

1. Visit the [live demo](https://modronic.github.io/Quran-Radio/)
2. Tap the **۞ symbol** or the **▶ play button** to start listening
3. Adjust volume with the slider — on iOS, use your device's physical volume buttons
4. Tap **■** to stop playback
5. Use **⏰ مؤقت** to set a sleep timer (20 / 30 / 45 / 90 minutes)
6. Tap **📤 مشاركة** to share — works on every device
7. Tap **⟳ تحديث** to do a full emergency refresh and clear all caches

### 📱 PWA & Home Screen Installation

Adding to your home screen gives you true full-screen mode, background audio, and lock screen controls.

| Device | Steps |
|--------|-------|
| **iPhone / iPad** | Open in **Safari** → Tap **Share ⎋** → "Add to Home Screen" → Open from home screen |
| **Android (Chrome)** | Tap **⋮** → "Install app" or "Add to Home Screen" → Open from app drawer |
| **Android (Samsung)** | Tap **⋮** → "Add page to" → "Home screen" |
| **macOS (Safari)** | File menu → "Add to Dock" |
| **Windows (Chrome/Edge)** | Click the install icon **⊕** in the address bar |

> 💡 **After installing:** playback continues in the background and you get play/pause controls on your lock screen and notification shade.

### 🖥️ Full-Screen in Browser

| Device | How |
|--------|-----|
| **Windows** | `F11` (press again to exit) |
| **macOS** | `Control ⌃ + Command ⌘ + F` or green maximize button |
| **Any Browser** | Tap the fullscreen icon ⧉ in the address bar |

---

## 🛠️ For Developers

### Quick Start

No build step. No package manager. No server required.

```bash
git clone https://github.com/modronic/Quran-Radio.git
cd Quran-Radio
# Open index.html directly in your browser — done.
```

### Project Structure

```
Quran-Radio/
└── index.html    # The entire application — HTML, CSS, and JS in one file
```

### Swapping the Stream

Find the `CAIRO_STREAM_URLS` array near the top of the `<script>` block:

```javascript
const CAIRO_STREAM_URLS = [
    "https://stream.radiojar.com/8s5u5tpdtwzuv",   // Primary CDN
    "https://n03.radiojar.com/8s5u5tpdtwzuv",      // Backup 1
    "https://n04.radiojar.com/8s5u5tpdtwzuv",      // Backup 2
    "https://n0e.radiojar.com/8s5u5tpdtwzuv"       // Backup 3
];
```

Replace with any `.mp3` or `.aac` stream URL. Add more backup URLs as needed — the failover logic handles the rest automatically.

### Changing the Share URL

```javascript
const SHARE_URL = 'https://modronic.github.io/Quran-Radio/';
```

Update this to your own deployment URL.

### Debug Mode

```javascript
const DEBUG = false; // Set to true to enable console logging
```

---

## 🌍 Device & Browser Compatibility

The app is intentionally built to run on **everything** — not just modern browsers.

| Platform | Minimum Version | Notes |
|----------|-----------------|-------|
| iOS Safari | 10+ | Volume slider hidden on iOS (device buttons used) |
| Android Chrome | 43+ | Full feature support |
| Samsung Internet | 4+ | Full feature support |
| Firefox Desktop | 63+ | Clipboard copy (no native share API) |
| Chrome Desktop | 66+ | Native share sheet on Windows 10/11 |
| Edge | 93+ | Native share sheet on Windows |
| macOS Safari | 13.1+ | Native share sheet |
| Smart TVs | Any | Tier 1 or Tier 4 share depending on browser |
| WebViews / In-App | Any | In-page URL overlay for share |
| IE11 | — | Basic playback only; share falls to in-page overlay |

---

## ⚙️ Technical Notes

- **Audio**: Uses HTML5 `<audio>` with `crossOrigin="anonymous"` for non-Firefox/WebView contexts
- **iOS Audio**: Locked to volume 1.0 with `playsinline` and `webkit-playsinline` attributes
- **WebView Detection**: Identifies Facebook, Instagram, TikTok, Twitter, WhatsApp, WeChat, Telegram, Snapchat, and generic Android WebViews
- **Prayer Times**: Fetched from `api.aladhan.com` using Cairo coordinates, Method 5 (Egyptian General Authority)
- **Hijri Date**: Displayed alongside prayer countdown, updated daily
- **Cache Clearing**: Emergency refresh wipes localStorage, sessionStorage, all Cache Storage entries, and unregisters any service workers before hard-reloading with a timestamp query
- **Media Session API**: Sets artwork, title, and play/pause/stop handlers for lock screen integration

---

## 📄 License

MIT — use freely, fork respectfully.

---

<div align="center">


*Made with care for the listeners of the Holy Quran*

</div>
