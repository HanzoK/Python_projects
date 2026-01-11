# Quizzler (True / False Quiz App)

A GUI-based **True/False quiz game** built with **Python**, **Tkinter**, and live trivia data from the **Open Trivia Database API**.  
Questions are fetched dynamically, displayed one by one, and scored in real time with instant visual feedback.

---

## Table of Contents

- [Preview](#preview)
- [Features](#features)
- [Requirements](#requirements)
- [How to Run](#how-to-run)
- [Controls](#controls)
- [Gameplay Rules](#gameplay-rules)
- [Program Flow Overview](#program-flow-overview)
- [API Usage](#api-usage)
- [Customization](#customization)
- [Credits](#credits)

---

## Preview

- Fetches **10 True/False questions** from an online trivia API
- Displays questions in a clean Tkinter UI
- Click **True** or **False** to answer
- Instant feedback:
  - ✅ Green for correct
  - ❌ Red for incorrect
- Live score tracking during the quiz

---

## Features

- Dynamic question loading from Open Trivia DB
- GUI-based quiz interface (no terminal input)
- HTML entity decoding for clean question text
- Real-time score updates
- Visual feedback after each answer
- Automatic quiz termination when questions are exhausted

---

## Requirements

- Python **3.x**
- `requests`

Standard library modules used:
- `tkinter`
- `html`

> Note: Requires an active internet connection to fetch questions.

---

## How to Run

1. Clone the repository:
```
git clone <repo-url>
cd <repo-folder>
```
2. Install dependencies:
```
pip install requests
```
3. Run:
```
python3 main.py
```
---

## Controls

| Action | Input |
|------|------|
| Answer “True” | ✅ True button |
| Answer “False” | ❌ False button |

---

## Gameplay Rules

- The quiz loads a fixed number of questions (default: 10)
- Each question is **True / False**
- After selecting an answer:
- The background flashes **green** if correct
- **Red** if incorrect
- Score increments only on correct answers
- When all questions are answered:
- Buttons are disabled
- A completion message is shown

---

## Program Flow Overview

1. Fetch questions from the Open Trivia API
2. Convert raw API data into `Question` objects
3. Initialize the quiz logic (`QuizBrain`)
4. Launch the Tkinter UI
5. For each question:
- Display question text
- Wait for user input
- Validate the answer
- Update score and UI
6. End the quiz when no questions remain

---

## API Usage

Questions are fetched from:
```
https://opentdb.com/api.php
```
Default parameters:
- `amount=10`
- `type=boolean`

You can optionally enable categories (for example: Computer Science = `18`) by adding:
```
"category": 18
```

## Customization

You can easily extend or modify the quiz:
- Change number of questions:
  - Update amount in the API parameters
- Add categories:
  - Use Open Trivia DB category IDs
- Adjust feedback delay:
  - Change window.after(1000, ...)
- Improve scoring:
  - Add a final score screen or percentage
- Add difficulty filtering:
  - Use the API’s difficulty parameter
---
## Credits

Quiz application built with Python, Tkinter, and the Open Trivia Database API.
