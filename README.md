# 🌀 Pião da Casa Própria in CSS 3D

> **Interactive draw for group presentations, team activities and events**, inspired by Silvio Santos' legendary game on Brazilian TV (SBT).

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)](https://en.wikipedia.org/wiki/HTML5)
[![CSS3 3D](https://img.shields.io/badge/CSS3-3D_Transforms-1572B6?style=flat-square&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transforms/Using_CSS_transforms)
[![Vanilla JS](https://img.shields.io/badge/JavaScript-Vanilla-F7DF1E?style=flat-square&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Zero Dependencies](https://img.shields.io/badge/dependencies-0-success?style=flat-square)](#)

---

## 📖 Overview

**Pião da Casa Própria** recreates the classic TV game using only native web technologies (**HTML5, CSS 3D transforms and plain JavaScript**, no frameworks or libraries).

Made for:
- 👥 **Drawing group members and presentation order** in school and university assignments;
- 🎤 **Event activities, meetups and parties**;
- 🎁 **Prize, number and team draws**.

---

## ✨ Features

### 1. 🌀 Spin the top with your finger (or mouse)
- **Double-tap** (or double-click) the top: it spins and draws.
- **Drag** horizontally: the drum follows your finger; on release, the gesture's speed sets the strength and duration of the spin (~1.5 to 6 s). Weak gestures just realign it without drawing.
- Realistic deceleration that stops exactly on the drawn face; spins last at least ~4 s and never more than 7 s.

### 2. 🎛️ Icon controls
A row of icons at the top of the screen, no settings panel (hover over an icon to see what it does):

| Icon | Function |
| :--- | :--- |
| **− 6 +** | Number of faces (2 to 15) |
| **123 / ABC** | Faces show numbers or letters |
| **No repeats** | One-at-a-time mode: faces already drawn won't come up again; when everyone has been drawn, double-tap restarts. In sequence mode it is always on (locked) |
| **Draw all** | Sequence mode: draws every face, one at a time, without repeats (each spin lasts a random 4–7 s) |
| **Sound** | Turns the soundtrack on/off |
| **Fullscreen** | Desktop only |

Nothing is saved: reloading the page always goes back to the initial state (6 faces, numbers, one at a time, sound on).

### 3. 📐 Realistic 3D drum (2 to 15 faces)
- **TV look**: like the show, the drum fills the ring's window — the front face's corners sit right behind the red ring and the side faces are cut by it — over an almost black backdrop, with large heavy white numbers. ~85 mm lens perspective: true proportions, little distortion.
- **Per-face projection**: each face gets its own transform, without relying on the browser's 3D plane sorting (`preserve-3d`), so it renders the same in Safari, Chrome and Firefox.
- **Constant sizing**: for any number of faces, the front face's corners stay on the ring's inner edge; below 6 faces, each face keeps the proportions of the 6-face drum.
- **Blinn-Phong lighting** (flat shading): a key light from the upper left with ambient, diffuse and specular terms; the highlight sweeps across the faces while spinning. Every shadow and highlight in the scene follows the same light direction.
- **Ambient occlusion** at the panel seams and next to the ring, plus a **contact shadow** of the drum on the backdrop.

### 4. 🏆 Results on screen
- A discreet strip below the top shows the results in the order they came out (the latest highlighted).
- Always visible, with **Stop** (enabled only while spinning: ends the current spin on the drawn face, or stops the sequence), **Copy order** and **Reset**.

### 5. 🎵 Soundtrack with the Web Audio API
- The soundtrack is decoded once and played through the Web Audio API, unlocked on the first tap: it plays reliably on every spin, including on iPhone ("playback" audio session, so the silent switch doesn't mute it).

---

## 🚀 Running

It's a 100% static app: no dependencies to install and no build step. The soundtrack is loaded with `fetch`, so **the files must be served over HTTP** (opening `index.html` straight from disk works, but without music):

```bash
# With Python 3
python3 -m http.server 8080

# Or with Node.js
npx serve .
```
Then open **`http://localhost:8080`** in the browser.

---

## ⌨️ Shortcuts and controls

| Action | Control |
| :--- | :--- |
| **Spin** | Double-tap / double-click the top, **[Enter]** or **[Space]** (hold for more strength) |
| **Spin with gesture strength** | Drag the top horizontally and release |
| **Stop** | **Stop** button in the results strip, double-tap the top or **[Esc]** (sequence) |
| **Sound on / off** | Sound icon or **[S]** |
| **Fullscreen** | Fullscreen icon or **[F]** (desktop) |

---

## 🛠️ Files

```
piao/
├── index.html                           # HTML5 structure, CSS 3D styles and JS logic
├── README.md                            # Documentation
├── piao-da-casa-propria-soundtrack.mp3  # Soundtrack (MP3)
├── piao-da-casa-propria-soundtrack.m4a  # Soundtrack (M4A)
└── piao-da-casa-propria-soundtrack.ogg  # Soundtrack (OGG)
```

- **No external dependencies**: no React, no Vue, no jQuery, no Tailwind.
- **GPU-accelerated CSS 3D**: 3D transforms and rotations are composited on the GPU.
- **Modern, compatible syntax**: works in Chrome, Safari, Firefox, Edge and mobile browsers.

---

## 📜 Credits and references

- Original concept by [Loop Infinito](http://loopinfinito.com.br/2012/05/13/piao-da-casa-propria-em-css-3d/) (2012).
- Inspired by the classic segment of **Baú da Felicidade / SBT (Sistema Brasileiro de Televisão)**, hosted by Silvio Santos.
