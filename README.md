<div align="center">

# ⚡ ENIGMA #1 — Cyberpunk Riddle Game

<img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5"/>
<img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS3"/>
<img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="JavaScript"/>
<img src="https://img.shields.io/badge/Web_Audio_API-FF6600?style=for-the-badge&logo=audiomack&logoColor=white" alt="Web Audio API"/>
<img src="https://img.shields.io/badge/PWA-5A0FC8?style=for-the-badge&logo=pwa&logoColor=white" alt="PWA"/>

<br/><br/>

> *A role-playing game in the real world, where reality changes face and riddles await you.*

<br/>

### 📲 Scan to Play

<img src="./qr_code_enigma_1.jpg" alt="Scan to play Enigma #1" width="250"/>

*Scan the QR code to start the adventure*

---

</div>

## 🎯 What is Enigma #1?

**Enigma #1** is the first of **10 riddles** hidden in the real world as QR codes. By scanning the code, the player is thrown into an interactive cyberpunk experience where they must solve a puzzle based on the **binary representation of numbers**.

The system generates a **random secret number** (from 1 to 60), hides it within 6 folders, and guides the player — through an immersive narrative introduction — to the resolution of the riddle.

---

## ✨ Key Features

| Feature | Description |
|:---|:---|
| 🧩 **Binary Riddle** | Puzzle based on decomposition into powers of 2 |
| 🎵 **Generative Music** | Cyberpunk soundtrack generated via Web Audio API (zero external files) |
| 📱 **PWA Ready** | Installable as an app, fullscreen support, safe-area for iOS notch |
| ⚡ **Cinematic Effects** | Interactive particle field, grain overlay, vignette, HUD corners, scan lines |
| 🔐 **Dynamic Password** | Each playthrough generates a unique password to unlock the next riddle |
| 🎨 **Zero Dependencies** | Single HTML file, no frameworks, no external assets (only Google Fonts) |

---

## 🕹️ How It Works

```
┌─────────────┐     ┌─────────────┐     ┌─────────────┐     ┌─────────────┐
│  QR Code    │────▶│  Narrative  │────▶│  Binary     │────▶│  Answer     │
│  Scan       │     │  Intro      │     │  Folders    │     │  & Password │
└─────────────┘     └─────────────┘     └─────────────┘     └─────────────┘
```

1. **Scan** the QR code hidden in the real world
2. **Read** the narrative introduction (13 pages with cinematic transitions)
3. **Explore** the 6 folders — each one tells you if the secret number is present or not
4. **Calculate** the number by summing the first value of each "correct" folder
5. **Enter** the answer and receive the **password** for the next riddle

---

## 🧠 The Riddle Logic

Each folder contains numbers that share a specific **bit** in their binary representation:

| Folder | First Number | Power of 2 | Bit |
|:------:|:------------:|:----------:|:---:|
| 6 | **32** | 2⁵ | `100000` |
| 5 | **16** | 2⁴ | `010000` |
| 4 | **8** | 2³ | `001000` |
| 3 | **4** | 2² | `000100` |
| 2 | **2** | 2¹ | `000010` |
| 1 | **1** | 2⁰ | `000001` |

> **Example:** if the secret number is **37** → `100101` in binary → present in folders **6** (32), **3** (4) and **1** (1) → 32 + 4 + 1 = **37** ✓

---

## 🎨 Tech Stack

```
enigma-1/
│
├── index.html          ← The entire game in a single file
│
├── Internal structure:
│   ├── HTML            → Semantic structure, inline PWA manifest
│   ├── CSS             → Glassmorphism panels, CSS animations, responsive
│   ├── JavaScript      → Game logic, Canvas particles, Web Audio API sequencer
│   └── Canvas          → Interactive particle field with mouse/touch reactivity
│
└── External dependencies:
    └── Google Fonts    → Outfit + Space Grotesk + Syne Mono
```

### Visual Effects
- Interactive particle field with connections (Canvas 2D)
- Noise grain overlay with animated shift
- Cinematic vignette & subtle scan lines
- HUD corner markers (sci-fi frame)
- Glassmorphism panels with backdrop-filter
- Card selection flash with glow accents
- "Overload" effect with screen flash on victory
- Danger shake with red flash on wrong answer

### Audio (Web Audio API)
- Synthesized **Kick**, **Snare**, **Hi-Hat**
- **Bass** with resonant filter
- **Lead synth** with sawtooth wave
- **Arpeggiator** with semitone pattern
- **Pad** with chord changes (Am → D → C → E)
- **Sequencer** at 110 BPM with section structure

---

## 🚀 Usage

### Option 1 — Direct opening
Open `index.html` in any modern browser. No server required.

### Option 2 — Local server (for PWA)
```bash
# With Python
python -m http.server 8000

# With Node.js
npx serve .
```
Then visit `http://localhost:8000`

### Option 3 — Deploy
Upload the file to any static hosting (GitHub Pages, Netlify, Vercel) and generate a QR code pointing to the URL.

---

## 📱 Compatibility

| Platform | Status |
|:---|:---:|
| Chrome (Desktop & Mobile) | ✅ |
| Safari (iOS) | ✅ |
| Firefox | ✅ |
| Samsung Internet | ✅ |
| PWA (Add to Home Screen) | ✅ |
| Fullscreen API | ✅ |

---

## 🔧 Customization

| Parameter | Where | Default |
|:---|:---|:---|
| Number range | `Math.floor(Math.random() * 60) + 1` | 1–60 |
| Music BPM | `60 / 110` in audio engine | 110 |
| Theme colors | CSS variables `:root` | Cyan / Magenta / Violet |
| Intro texts | `PAGES` array | English |
| Password prefix | `'ENIGMA2-'` | ENIGMA2- |
| Particle count | `for (let i = 0; i < 80; i++)` | 80 |

---

## 🚧 Work In Progress

<div align="center">

**This project is actively being developed.**

Enigma #1 is just the beginning — **9 more riddles** are on the way, each with increasing difficulty, new puzzle mechanics, and unique cyberpunk aesthetics.

| Riddle | Status | Difficulty |
|:------:|:------:|:----------:|
| #1 — Binary Folders | ✅ Complete | ⭐ |
| #2 | 🔧 In progress | ⭐⭐ |
| #3 | 📋 Planned | ⭐⭐ |
| #4 | 📋 Planned | ⭐⭐⭐ |
| #5 | 📋 Planned | ⭐⭐⭐ |
| #6 | 📋 Planned | ⭐⭐⭐⭐ |
| #7 | 📋 Planned | ⭐⭐⭐⭐ |
| #8 | 📋 Planned | ⭐⭐⭐⭐ |
| #9 | 📋 Planned | ⭐⭐⭐⭐⭐ |
| #10 — Final Challenge | 📋 Planned | ⭐⭐⭐⭐⭐ |

*Stay tuned. The adventure has only just begun.*

</div>

---

<div align="center">

**Built with ⚡ and a whole lot of cyberpunk energy**

*Good luck... you'll need it.*

</div>
