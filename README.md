# ⏱️ Vintage Chronometer

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![No Dependencies](https://img.shields.io/badge/Dependencies-Zero-brightgreen?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-gold?style=for-the-badge)

---

## 🔍 Overview

**Vintage Chronometer** is a dual-mode stopwatch and countdown timer engineered as a single-file, zero-dependency web application — styled as a precision mechanical stopwatch with a fully interactive vintage dial.

Architected entirely in vanilla HTML, CSS, and JavaScript, the application persists its complete state — elapsed time, running/paused status, and countdown target — to `localStorage`, enabling seamless resume on page refresh without any backend, framework, or build tool. The UI is driven by `requestAnimationFrame` for smooth, jank-free 60fps rendering of the sweep hand, sub-dial, and countdown arc. Mode switching between Stopwatch and Timer is instant, with independent state per mode.

Designed for environments where reliability and portability matter — a single `.html` file that runs offline, deploys to any static host, and requires no installation whatsoever.

---

## 🌍 Real-World Use Cases

| Domain | Application |
|---|---|
| 🏋️ Fitness & Sports | Interval training timers, lap timing, rest-period countdowns between sets |
| 🍳 Kitchen & Cooking | Precise cooking countdowns with audio alarm — no app install needed |
| 🎓 Education | Classroom exam timers displayed on projector; quiz countdown from browser |
| 🏥 Healthcare | Procedure timing and medication interval tracking at the bedside |
| 🎮 Gaming | Speed-run timing, puzzle challenge countdowns, tournament clock display |
| 🏭 Industrial / QA | Process step timing on factory floor — offline-capable, no network required |

---

## ⚡ Features

- **Engineered** a dual-mode interface — Stopwatch and Countdown Timer — switchable mid-session without state loss
- **Implemented** full `localStorage` persistence so elapsed time, running state, and countdown target survive page refresh or tab close
- **Built** a vintage mechanical dial UI with SVG tick marks, conic-gradient metallic rings, sweep second hand, and a sub-dial minute tracker — zero images used
- **Designed** a live countdown arc ring that depletes visually around the dial face and shifts from gold to red in the final 10 seconds
- **Integrated** a Web Audio API alarm system — a 6-note chime fires on countdown completion with no external audio files
- **Automated** alarm re-trigger on page restore: if the countdown expired while the tab was closed, the alarm fires immediately on reload
- **Implemented** tick sound toggle via Web Audio API oscillator — zero audio file dependencies
- **Optimized** all rendering via `requestAnimationFrame` — smooth 60fps hand animation with no `setInterval` drift

---

## 🛠️ Tech Stack

| Layer | Technology | Purpose |
|---|---|---|
| Structure | HTML5 | Semantic single-file document layout |
| Styling | CSS3 (Custom Properties, conic-gradient, SVG) | Vintage dial aesthetics, animations, responsive layout |
| Logic | Vanilla JavaScript (ES6+) | Timer engine, state machine, persistence, audio |
| Rendering | `requestAnimationFrame` | Smooth 60fps hand and arc updates |
| Persistence | Web Storage API (`localStorage`) | Cross-refresh state: elapsed time, mode, countdown target |
| Audio | Web Audio API | Tick sounds and alarm chime — no audio files |
| Fonts | Google Fonts (Cinzel, Share Tech Mono) | Vintage serif branding + monospace digital display |
| Deployment | Any static host (GitHub Pages, Netlify, Render, Cloudflare Pages) | Zero build step — single `.html` file |

---

## 📁 Project Structure

```
vintage-chronometer/
│
├── stopwatch.html          # Complete application — HTML + CSS + JS in one file
├── README.md               # Project documentation
├── LICENSE                 # MIT License
│
└── docs/                   # Screenshots and demo assets
    ├── sample_stopwatch.png
    └── sample_timer.png
```

> No `node_modules`, no `requirements.txt`, no build pipeline.
> Open `stopwatch.html` in any browser and it works — including offline.

---

## 🚀 Installation & Setup

### Prerequisites
- Any modern browser (Chrome, Firefox, Safari, Edge)
- No Python, Node, or package manager required

### 1. Clone the Repository
```bash
git clone https://github.com/MdRayyanKalkoti/vintage-chronometer.git
cd vintage-chronometer
```

### 2. Open in Browser

**Option A — Direct file open:**
```bash
open stopwatch.html          # macOS
start stopwatch.html         # Windows
xdg-open stopwatch.html      # Linux
```

**Option B — Serve locally (optional, for development):**
```bash
# Python 3
python -m http.server 8000

# Then open: http://localhost:8000/stopwatch.html
```

> No environment variables. No `.env` file. No API keys. No server.

---

## 🖥️ Usage Guide

### Stopwatch Mode
| Action | How |
|---|---|
| Start | Click **Start** button or tap the **Crown Knob** at the top of the dial |
| Pause | Click **Pause** or tap the Crown Knob again |
| Resume | Click **Resume** or Crown Knob |
| Reset | Click **Reset** or the **Left Side Button** on the dial |
| Clear All | Click **Clear All** — wipes localStorage and resets everything to zero |

### Timer Mode
1. Click the **Timer** tab at the top
2. Enter your desired countdown in the `HH : MM : SS` input fields
3. Press **Set Timer** (or hit `Enter`)
4. Click **Start** — the arc ring begins depleting around the dial
5. At zero — alarm fires, dial flashes red, status dot pulses

### Persistence Behaviour
| State at close | Behaviour on reopen |
|---|---|
| Stopwatch running | Resumes from correct elapsed time |
| Stopwatch paused | Shows last frozen time |
| Timer running | Resumes countdown from correct remaining time |
| Timer expired while closed | Alarm fires immediately on page load |
| Timer paused | Shows remaining time |

---

## 📸 Demo

| Stopwatch Mode | Timer Mode — Final 10s |
|---|---|
| ![Stopwatch](docs/sample_stopwatch.png) | ![Timer](docs/sample_timer.png) |

---

## ☁️ Deployment

This project deploys with **zero configuration** to any static hosting platform.

### Cloudflare Pages (Recommended)
1. Push repository to GitHub
2. Go to [pages.cloudflare.com](https://pages.cloudflare.com) → **Create a project**
3. Connect your GitHub repository
4. Set build settings:

| Setting | Value |
|---|---|
| Build command | *(leave empty)* |
| Build output directory | `/` |

5. Click **Deploy** — live in under 60 seconds, global CDN, automatic HTTPS

### GitHub Pages
```bash
# In repo settings → Pages → Source → Deploy from branch → main → / (root)
# Your app is live at: https://MdRayyanKalkoti.github.io/vintage-chronometer/stopwatch.html
```

### Netlify / Render
Drag and drop `stopwatch.html` into the Netlify dashboard — no configuration needed.

---

## 🌐 Live Demo

👉 **[https://your-app.pages.dev](https://your-app.pages.dev)** *(replace with deployed URL)*

---

## 💡 Why This Project Matters

Browser-based timers are a solved problem — until you need one that **survives a page refresh, requires no server, runs offline, and looks like it belongs on a watchmaker's bench**.
   
Most existing solutions fail because:
- They reset on refresh — relying on in-memory state with no persistence layer
- They depend on frameworks (React, Vue) that add hundreds of KB of overhead for a timer
- They use `setInterval` which drifts under CPU load — producing incorrect elapsed times
- They require a backend or network connection for basic functionality

This project addresses all of these by using `Date.now()` anchored timestamps (not tick-counted intervals), `localStorage` for zero-backend persistence, and `requestAnimationFrame` for smooth rendering — the same architectural approach used in production time-tracking and scheduling tools.

The result is a **portable, offline-capable, production-reliable** timing system that deploys as a single file, loads in milliseconds, and works correctly whether it has been open for 3 seconds or 3 hours.

---

## 🤝 Contributing

Pull requests are welcome. For significant changes, please open an issue first.

```bash
# Fork the repository
git checkout -b feature/your-feature
git commit -m 'Add: your feature'
git push origin feature/your-feature
# Open a Pull Request
```

---

## 👤 Author

**Md Rayyan**
AI Engineer | Backend Developer

[![GitHub](https://img.shields.io/badge/GitHub-MdRayyanKalkoti-181717?style=flat&logo=github)](https://github.com/MdRayyanKalkoti)

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

<p align="center">
  Built with precision by <a href="https://github.com/MdRayyanKalkoti">Md Rayyan</a> · Engineered for production, not portfolios.
</p>