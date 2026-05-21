# 🎉 GDG Doorprize Picker

A beautiful, browser-based doorprize picker for GDG events. Randomly selects **3 winners** from a participant list with a slot-machine animation, winner history, and participant management — all with no server or dependencies required.

---

## 📁 Files

| File | Description |
|------|-------------|
| `doorprize.html` | Main app — open this in any browser |
| `transformed_names.json` | Source list of participant names |
| `README.md` | This file |

---

## 🚀 Getting Started

1. Open `doorprize.html` in any modern browser (Chrome, Edge, Firefox).
2. No installation, build step, or internet connection required.

---

## ✨ Features

### 🎲 Draw Winners
- Randomly picks **3 unique winners** from the participant pool.
- Animated **slot-machine rolling effect** before revealing each winner.
- Winners are displayed with 🥇 Gold / 🥈 Silver / 🥉 Bronze rankings.
- Full-screen **confetti blast** fires on every draw.

### ✂️ Remove Winners from Participants
- After a draw, click **"Remove Winners from Participants"** to instantly remove all 3 winners from the pool.
- Prevents the same names from being drawn again in subsequent rounds.
- Button is disabled until a draw is made, and resets after use.

### 👥 Participant Management
- Full scrollable list of all remaining participants.
- **Live search** to filter by name.
- **Remove any participant** individually with the ✕ button before or after a draw.
- Participant count updates in real time.

### 📜 Winner History
- Every draw is automatically saved to `localStorage` — history persists across page reloads.
- Each entry shows the **round number**, **timestamp**, and all 3 winners.
- **Clear History** button with a confirmation prompt.

---

## 🛠 Customising the Participant List

The participant names are embedded directly in `doorprize.html` inside the `NAMES_JSON` array (line ~385):

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
- **Vanilla CSS** — glassmorphism dark UI, animations, responsive grid
- **Vanilla JavaScript** — draw logic, localStorage persistence, confetti engine
- **Google Fonts** — Inter & Space Grotesk

No frameworks. No dependencies. One file.

---

## 📸 UI Overview

| Panel | Description |
|-------|-------------|
| **Winners** | Displays the 3 drawn winners with draw & remove buttons |
| **Participants** | Searchable list with per-name removal |
| **Winner History** | Chronological log of all past draws |

---

## 📝 Notes

- Winner history is stored in `localStorage` under the key `gdg_doorprize_history`.
- Clearing browser data will erase the history.
- The app works fully offline after the Google Fonts stylesheet loads (or even without it, falling back to system fonts).
