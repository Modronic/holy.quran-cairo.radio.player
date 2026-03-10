# 🌙 Sakeena FM - Currently Streaming Cairo Quran Radio Channel
            Live from Cairo, Egypt


![Status](https://img.shields.io/badge/status-ready-brightgreen?style=for-the-badge)
![License](https://img.shields.io/badge/license-MIT-blue?style=for-the-badge)

A beautiful, minimalist web application for listening to the Holy Quran in radio style live from Cairo. Built with pure HTML, CSS, and JavaScript — **zero dependencies**, **single HTML file**, **respectful design**.

> "وَإِذَا قُرِئَ الْقُرْآنُ فَاسْتَمِعُوا لَهُ وَأَنْصِتُوا لَعَلَّكُمْ تُرْحَمُونَ"  
> — سورة الأعراف، الآية ٢٠٤

[🎧 Live Demo](https://modronic.github.io/holy.quran-cairo.radio.player/) | [📱 Install on Home Screen](#pwa-support)

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| **Pure Vanilla** | Zero frameworks, zero dependencies — single HTML file |
| **Beautiful UI** | Sacred ۞ symbol with breathing animations, glassmorphism design |
| **Smart Streams** | Primary + 2 backup streams with automatic failover |
| **Respectful UX** | Clean interface focused on Quranic listening experience |
| **Mobile Perfect** | Works flawlessly on iOS, Android, all browsers |
| **PWA Ready** | Install on home screen for background playback |
| **Console Clean** | Zero errors or warnings in production |
| **Lightweight** | ~46KB total — loads in under 1 second |

---

## ❔ How to Use

### For Listeners
1. Visit the [live demo](https://modronic.github.io/holy.quran-cairo.radio.player/)
2. Click the **۞ symbol** or the play button to start listening
3. Adjust volume with slider (iOS: use device volume buttons)
4. Click **■** to stop playback

### 📱 Full-Screen Instructions (All Devices)

| Device | How to Full-Screen |
|--------|-------------------|
| **Windows PC** | Press `F11` key (press again to exit) |
| **macOS** | Click green maximize button **or** `Control + Command + F` |
| **iPhone/iPad** | Open in **Safari** → Tap **Share (⋮)** → "Add to Home Screen" → Open from home screen |
| **Android** | Open in **Chrome** → Tap **⋮** → "Install app" → Open from app drawer |
| **Any Browser** | Tap the browser's fullscreen icon (⧉) in address bar |

> 💡 **Pro Tip:** For iOS/Android, **adding to home screen** gives true full-screen mode with background playback — much better than browser tab!

### For Developers
1. Fork this repository
2. Replace stream URLs in `index.html`:

```javascript
const STREAM_URLS = [
    "YOUR_PRIMARY_STREAM_URL_HERE",
    "YOUR_BACKUP_STREAM_URL_1_HERE",
    "YOUR_BACKUP_STREAM_URL_2_HERE"
];
