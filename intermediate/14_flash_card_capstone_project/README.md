# Flashy (French → English Flashcards)

A simple **flashcard app** built with **Tkinter** and **Pandas** to practice French vocabulary.  
Cards flip automatically after a short delay, and words you already know are removed from the learning pool.

---

## Table of Contents

- [Preview](#preview)
- [Features](#features)
- [Project Structure](#project-structure)
- [Requirements](#requirements)
- [How to Run](#how-to-run)
- [Controls](#controls)
- [Gameplay Rules](#gameplay-rules)
- [Game Loop Overview](#game-loop-overview)
- [Customization](#customization)
- [Credits](#credits)
  
---

## Preview

- Shows a **French** word first
- Automatically flips to the **English** translation after ~3 seconds
- ✅ Click **right** if you knew it (removes it from the deck)
- ❌ Click **wrong** to keep it and move to the next card
- Progress is saved to `words_to_learn.csv`

---

## Features

- Flashcard UI with front/back card images
- Auto-flip timer (French → English)
- Random word selection from a CSV dataset
- Persistent progress:
  - Known words are removed from future sessions
  - Remaining words are saved to `./data/words_to_learn.csv`
- Graceful exit when no words remain

---

**What each file does:**
- `main.py` — Tkinter UI, card flipping logic, progress saving
- `./data/french_words.csv` — original vocabulary list (French/English)
- `./data/words_to_learn.csv` — auto-generated learning list (your remaining words)
- `./images/card_front.png` — flashcard front image
- `./images/card_back.png` — flashcard back image
- `./images/right.png` — “I knew it” button image
- `./images/wrong.png` — “I didn’t know it” button image

---

## Requirements

- Python **3.x**
- `pandas` (for CSV loading/saving)
- Tkinter (usually included with Python)

> Note: This app opens a GUI window and needs a graphical environment.

---

## How to Run

1. Clone the repository:
```
git clone <repo-url>
cd <repo-folder>
```
2. Install dependencies
```
pip install pandas
```
3. Run
```
python3 main.py
```
---

## Controls

| Action | Button |
|--------|--------|
| Mark as “known” (remove from deck) | ✅ Right button |
| Mark as “unknown” (keep learning) | ❌ Wrong button |

---

## Gameplay Rules

- The app tries to load your progress first:
- If `./data/words_to_learn.csv` exists → it uses that
- Otherwise → it loads the full list from `./data/french_words.csv`
- Each round:
- A French word is shown
- After ~3 seconds, the card flips to English
- If you click ✅ (known):
- The current word is removed from the list
- The remaining words are saved back to `words_to_learn.csv`
- If you click ❌ (unknown):
- The word stays in the list
- The app moves on to another card
- When no words are left:
- The app prints a message and closes

---

## Game Loop Overview

The app runs on Tkinter’s event loop (`mainloop()`), using:

1. `generate_word()` to pick and display a new French word
2. `window.after(...)` to schedule an automatic flip after 3 seconds
3. `flip_card()` to reveal the English translation
4. Button callbacks:
- ✅ `already_knows()` saves progress and loads a new card
- ❌ `generate_word()` skips to the next card without removing the word

---

## Customization

You can tweak the learning behavior easily:

- Flip delay (currently 3 seconds):
- Change `3000` in:
 - `window.after(3000, flip_card)`
- Font sizes:
- Adjust the `create_text(...)` font settings
- Add more words:
- Edit `./data/french_words.csv` (must keep the `French` and `English` column names)
- Reset progress:
- Delete `./data/words_to_learn.csv` to restart from the full dataset

---

## Credits

Flashcard vocabulary trainer built with Python Tkinter and Pandas.
