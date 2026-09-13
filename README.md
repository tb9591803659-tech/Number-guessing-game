<div align="center">

# 🎮 NUMBER GUESSING GAME

**A feature-packed, CLI-based number guessing challenge written in Python.**  
*Beat the clock, conserve your hints, and climb the persistent leaderboard!*

[![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white)](#)
[![Colorama](https://img.shields.io/badge/Colorama-0.4.6+-F7B731?style=for-the-badge&logo=pypi&logoColor=white)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-41B883?style=for-the-badge)](#)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey?style=for-the-badge)](#)

<br />

[Features](#-key-features) • [Game Modes](#-game-modes) • [Scoring & Hints](#-hint-system--scoring) • [Quick Start](#-quick-start) • [Roadmap](#-future-roadmap)

</div>

---

## ✨ Key Features

- 🎚️ **Adaptive Difficulty:** 3 distinct modes with unique number ranges, timers, and attempt pools.
- ⏱️ **Active Countdown:** Background thread handles real-time countdown limits without freezing inputs.
- 💡 **Dynamic Hint Engine:** Distance-based proximity feedback (`🔥 Very Close` to `❄️ Far`).
- 🏆 **Weighted Scoring:** Dynamically balances speed, remaining attempts, and penalty deductions.
- 📊 **Persistent Records:** Local JSON-backed leaderboard storing scores across sessions.
- 🎨 **Rich CLI UI:** Fully colored interactive terminal interface powered by `colorama`.

---

## 🎮 Game Modes

| Mode | Range | Attempts | Timer | Multiplier |
| :--- | :---: | :---: | :---: | :---: |
| 🟢 **Easy** | `1 – 10` | 10 attempts | 300 sec | `1.0x` |
| 🟡 **Medium** | `1 – 50` | 7 attempts | 180 sec | `1.5x` |
| 🔴 **Hard** | `1 – 100` | 5 attempts | 60 sec | `2.0x` |

---

## 💡 Hint System & Scoring

### 🔍 Proximity Meter
Players can request up to **4 hints per match**. Feedback scales based on absolute distance to the secret number:

| Status | Distance ($\Delta$) | Indicator |
| :--- | :--- | :--- |
| **Direct Hit** | $\Delta = 0$ | 🎯 `Exact` |
| **Very Close** | $\Delta \le 3$ | 🔥 `Very Close` |
| **Close** | $3 < \Delta \le 10$ | ⚡ `Close` |
| **Far** | $\Delta > 10$ | ❄️ `Far` |

### 🧮 Score Formula
```text
Score = [ (Attempts_Left × 10) + Time_Remaining ] × Difficulty_Multiplier - (Hints_Used × 5)
```

## 🚀 Quick Start

### 1. Prerequisites
Ensure **Python 3.8+** is installed on your system:
```bash
python --version
```

### 2. Clone the repository
git clone [https://github.com/YOUR_USERNAME/number-guessing-game.git](https://github.com/YOUR_USERNAME/number-guessing-game.git)

### 3. Navigate to the project directory
cd number-guessing-game

### 4. Install external dependencies
pip install -r requirements.txt

### 5. Launch the game
python main.py

## 🔮 Future Improvements

Tracked below are planned enhancements and feature milestones for upcoming releases:

### 🎮 Gameplay & Mechanics
- [ ] **Difficulty-Scaled Hints:** Adjust the hint pool dynamically (e.g., Easy = 5 hints, Medium = 3 hints, Hard = 1 hint).
- [ ] **Match Analytics:** Track extended player stats including games played, win/loss ratio, and average guess speed.
- [ ] **Instant Replay Loop:** Add an in-terminal `"Play Again? (y/n)"` flow instead of returning to the main menu.
- [ ] **Audio Feedback:** Integrate cross-platform sound cues (ticks on low timer, win/loss chimes).

### 🛠️ Architecture & Code Quality
- [ ] **Modular Refactor:** Decompose `main.py` into discrete handlers:
  - `game.py` (core gameplay & thread timers)
  - `leaderboard.py` (JSON persistence & sorting)
  - `ui.py` (color formatting & terminal screens)
- [ ] **Automated Test Suite:** Implement comprehensive unit tests using `pytest` to validate scoring logic and boundary constraints.
- [ ] **CI/CD Integration:** Set up GitHub Actions for automated linting (`flake8`, `black`) on pull requests.

### 🖥️ Interface & Presentation
- [ ] **Enhanced Terminal Tables:** Upgrade leaderboard presentation using libraries like `rich` or `tabulate`.
- [ ] **GUI Variant:** Build a lightweight graphical desktop interface using Tkinter or PyQt.
- [ ] **Config File Support:** Support custom ranges, timers, and attempt counts via `config.json` or `.env`.

## 🤝 Contributing

Contributions are what make the open-source community an incredible place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

### 🛠️ How to Contribute

1. **Fork the Project**  
   Click the **Fork** button at the top right of this repository.

2. **Clone Your Fork**
   ```bash
   git clone [https://github.com/YOUR_USERNAME/number-guessing-game.git](https://github.com/YOUR_USERNAME/number-guessing-game.git)
   cd number-guessing-game
   ```

## 👤 Author

**Shashank T**

- GitHub: [@Shashankt_ai](https://github.com/tb9591803659-tech)
- LinkedIn: [@Shashank T](www.linkedin.com/in/shashank-t-765971388)
- Email: tb9902849177@gmail.com

---

## 📄 License

This project is open source and available under the terms of the [MIT License](LICENSE).

```text
MIT License

Copyright (c) 2026 Your Name

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```