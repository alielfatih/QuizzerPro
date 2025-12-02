# 📘 Quizzer Pro
Quizzer Pro is a modern, AI-augmented study tool designed for mastering medical MCQs using active recall, adaptive spaced repetition (FSRS), and performance-based difficulty adjustment.

This README provides complete documentation on how to use the app, manage decks, create JSON files, and understand the UI.

---

## User Guide
  [User Guide](docs/User_Guide_Json.md).
  ---
    Here you will find how to create your own json file manually,
    or you can create the file struture using and AI or our coming file genertor[feature]:
    you us an AI to convert your preexist MCQs like thi.
    
    ```
      use the rules in this destination https://gist.githubusercontent.com/alielfatih/90b370a0c06cd6527df48e7393537735/raw/e928611858f05e5f56994b61137ffa7b3b66effc/QuizzerPro_json_rules.md,
      then create x mcqs following those rules.
    ```
    then just copy & paste them into text file and save it json format
  

# 🚀 Features

### 🔹 Smart Adaptive Learning
- FSRS-inspired spaced repetition
- Leitner system integration (Boxes 1–5)
- Session generation based on:
  - Overdue items
  - New (unseen) questions
  - Weak mastery areas
  - Dynamically mixed difficulty

### 🔹 Session Persistence
- Automatically saves learning progress to `session_data.json`
- Restores stats, mastery scores, due dates, Leitner states
- Manual toggle in UI to enable/disable loading previous session

### 🔹 Deck Management System
- Save any loaded JSON as a **Deck** with a unique name
- Prevents saving duplicate deck content unless updated
- Select which deck to load in new sessions

### 🔹 Clean, Modern UI (CustomTkinter)
- Dark theme & medical color highlights
- Smooth layout
- Keyboard navigation
- Explanation panel with automatic formatting
- Restart button changes text dynamically:
  - `Start` when no session active
  - `Restart` during an active session

---

# 🖥️ Installation & Running

1. Download **Quizzer Pro.exe** from the release page.
2. Place it anywhere (portable).
3. Double-click to run.

The app uses:
- Python 3.10+ (if running source)
- CustomTkinter


---

# 🧩 JSON Deck Format (VERY Important)
Quizzer Pro loads MCQs from JSON files structured as follows.

```json
[
  {
    "question": "What is example X?",
    "options": ["Option A", "Option B", "Option C", "Option D"],
    "answer": "Option B",
    "explanations": {
      "Option A": "Reason A is incorrect",
      "Option B": "Reason B is correct",
      "Option C": "Reason C is incorrect",
      "Option D": "Reason D is incorrect"
    }
  }
]
```
---

# ⚠️ Case-Sensitivity Rules (Critical)
The `options[]` entries **must match exactly** the keys inside `explanations{}`.

That includes:
- Upper/lowercase letters
- Whitespaces
- Punctuation
- Symbols
- Accents

Example of **incorrect** mapping:

| Options[]         | Explanations key | Status |
|-------------------|------------------|--------|
| "option A"        | "Option A"       | ❌ mismatch |
| "Option  A"       | "Option A"       | ❌ mismatch |
| "Option-A"        | "Option A"       | ❌ mismatch |
| "option a"        | "Option A"       | ❌ mismatch |

Example of **correct** mapping:

| Options[]   | Explanations key | Status |
|-------------|------------------|--------|
| "Option A" | "Option A"       | ✔ perfect match |

If they do not match, the explanation will **not appear**.

---

# 📚 Creating Decks
You can:
- Load any `.json` file
- Edit using the built-in Deck Editor
- Save as a new deck
- Auto-detect updates

### Deck Storage
Decks are saved in a `decks/` folder.
- Duplicate content is prevented
- If you overwrite a deck's content, it automatically updates

---

# 🧠 Session Data Handling
Quizzer Pro stores progress in:
```
session_data.json
```
Automatically saved:
- Mastery score
- Stability, difficulty
- Leitner box level
- Due dates
- Total/Correct stats

You can disable loading previous session via a toggle.

If session file does not exist:
- A new one is created

---

# 🖱️ UI Overview
Here’s how the main interface works:

### Header
- App title

### Controls
- **Load JSON** — choose deck file
- **Save** — export modified deck
- **Add/Edit Q** — deck editor
- **Dashboard** — learning analytics
- **Start/Restart** — dynamic based on session

### Stats Bar
- Score
- Mastery percentage
- Repeat All toggle
- Session Load toggle (if enabled)

### Progress Bar
- Indicates completion of adaptive session

### Quiz Card
- Question text
- 4 MCQ options
- Explanation section
- Rating bar (1–4 FSRS)

---

# ⌨️ Keyboard Shortcuts
| Key | Action |
|-----|--------|
| ←, →, ↑, ↓ | Navigate options |
| Enter | Submit or auto-select FSRS rating |
| 1,2,3,4 | FSRS review rating |

---

# 📘 Example JSON Deck
```json
[
  {
    "question": "Which electrolyte imbalance causes peaked T-waves?",
    "options": ["Hyperkalemia", "Hypokalemia", "Hyponatremia", "Hypercalcemia"],
    "answer": "Hyperkalemia",
    "explanations": {
      "Hyperkalemia": "High K⁺ → peaked T-waves.",
      "Hypokalemia": "Low potassium causes U-waves.",
      "Hyponatremia": "Does not affect T-wave shape.",
      "Hypercalcemia": "Shortens QT interval."
    }
  }
]
```
---

# 🧰 Troubleshooting
### ✔ App closes instantly when double-clicking `.exe`
Usually caused by:
- Corrupt session file
- Missing write permission

Fix:
1. Delete `session_data.json`
2. Ensure folder is writable

### ✔ Explanations missing
Cause: options do not match explanation keys exactly.

---

# 🏁 Final Notes
Quizzer Pro is a powerful medical study companion using:
- Modern UI
- High-performance adaptive learning
- Deep tracking of mastery
- Auto-saving sessions
- Modular deck system

If you need:
- A full API reference
- An automatic JSON generator
- A validation tool for decks
- A tutorial for creating perfect decks

Just ask, and it will be added.

---

**Made by medical student for serious medical learners 🧠📚**


## Privacy Policy

Quizzer Pro is a local, offline app. Your data stays on your device. For more details, see our [Privacy Policy](PRIVACY.md).



