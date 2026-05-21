# 🎉 GDG Doorprize Picker

A stunning, browser-based doorprize picker for GDG events built with an **iOS-inspired glassmorphism** design. Randomly selects **3 winners** from a participant list with spring animations, winner history, and participant management — no server or dependencies required.

---

## 📁 Files

| File | Description |
|------|-------------|
| `doorprize.html` | Main app — open this in any browser |
| `transformed_names.json` | Source list of participant names |
| `README.md` | This file |

---

## 🚀 Getting Started

1. Open `doorprize.html` in any modern browser (Chrome, Edge, Firefox, Safari).
2. No installation, build step, or internet connection required *(Google Fonts loads on first open if online)*.

---

## ✨ Features

### 🎲 Draw Winners
- Randomly picks **3 unique winners** from the participant pool.
- Animated **slot-machine rolling effect** before each reveal.
- Winners displayed with 🥇 Gold / 🥈 Silver / 🥉 Bronze rankings.
- Color-coded **glow halos** on each revealed slot.
- Full-screen **confetti blast** fires on every draw.

### ✂️ Remove Winners from Participants
- After a draw, click **"Remove Winners from Participants"** to instantly remove all 3 winners from the pool.
- Prevents the same names from being drawn in future rounds.
- Button is disabled until a draw is made and auto-resets after use.

### 👥 Participant Management
- Full scrollable list of all remaining participants with **live search** filter.
- **Remove any participant** individually with the ✕ button — slides out with a smooth animation.
- Participant count updates in real time.

### 📜 Winner History
- Every draw is saved to `localStorage` — history persists across page reloads.
- Each entry shows the **round number**, **timestamp**, and all 3 winners.
- **Clear History** button with a confirmation prompt.

---

## 🎨 Design

The app uses an **iOS glassmorphism** aesthetic:

| Element | Detail |
|---------|--------|
| **Font** | [Plus Jakarta Sans](https://fonts.google.com/specimen/Plus+Jakarta+Sans) — all weights |
| **Background** | Animated multi-color gradient wallpaper (shifts like an iOS Live Wallpaper) |
| **Cards** | Frosted glass via `backdrop-filter: blur(28px) saturate(200%)` with inset highlight borders |
| **Colors** | iOS system palette — blue `#007AFF`, purple `#AF52DE`, green `#30D158`, red `#FF3B30` |
| **Animations** | Spring physics `cubic-bezier(0.34, 1.56, 0.64, 1)` on all reveals, hovers, and entry transitions |
| **Buttons** | iOS-blue gradient primary button + red glass secondary button |

---

## 🛠 Customising the Participant List

The participant names are embedded directly in `doorprize.html` inside the `NAMES_JSON` array (~line 210):

```js
const NAMES_JSON = [
  "Name One",
  "Name Two",
  // ...
];
```

To update the list, edit this array. The `transformed_names.json` file was the original source used to populate it.

---

## 🌐 Tech Stack

- **HTML5** — structure & semantics
- **Vanilla CSS** — iOS glassmorphism, `backdrop-filter`, animated gradient wallpaper, spring animations
- **Vanilla JavaScript** — draw logic, `localStorage` persistence, canvas confetti engine
- **Google Fonts** — Plus Jakarta Sans

No frameworks. No dependencies. One file.

---

## 📝 Notes

- Winner history is stored in `localStorage` under the key `gdg_doorprize_history`.
- Clearing browser data will erase the history.
- `backdrop-filter` (blur/glass effect) requires a Chromium or WebKit browser for full fidelity; Firefox supports it with a flag.
