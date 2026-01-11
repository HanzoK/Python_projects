# U.S. States Guessing Game (with Turtle & Pandas)

An interactive U.S. geography quiz built with Python’s **turtle** graphics and **pandas**.  
Players guess U.S. state names, which are then labeled directly onto a blank map of the United States.

---

## Preview

- Type U.S. state names to place them on the map
- Correct guesses appear at the correct geographic location
- Tracks how many states you’ve guessed out of 50
- Generates a `states_to_learn.csv` file for missed states

---

## Features

- Interactive text-input–based guessing game
- Visual map rendering using Turtle graphics
- Automatic placement of state names using coordinate data
- Duplicate-guess prevention
- Export of unguessed states for further study
- Clean separation of game logic and rendering logic

---

**What each file does:**
- `main.py` — game loop, input handling, validation, CSV export
- `state_class.py` — Turtle-based class for writing state names on the map
- `50_states.csv` — dataset containing state names and x/y coordinates
- `blank_states_img.gif` — background image of the U.S. map
- `states_to_learn.csv` — auto-generated list of missed states

---

## Requirements

- Python **3.x**
- `pandas`
- Turtle graphics (included with standard Python)

> Note: Turtle requires a graphical environment and will not run headless.

---



## How to Run

1. Clone the repository:
```
git clone <repo-url>
cd <repo-folder>
```
2. Install dependencies (if needed):
```
pip install pandas
```
3. Run the game:
```
python3 main.py
```
---

## Controls

| Action | Input |
|------|------|
| Guess a state | Type the state name |
| Quit game | Type `Exit` |

State names are case-insensitive and normalized automatically.

---

## Gameplay Rules

- The game continues until:
- All 50 states are guessed, or
- The player types `Exit`
- Correct guesses:
- Are written directly onto the map
- Increase the guessed-state counter
- Duplicate guesses are ignored
- Invalid guesses are skipped silently

---

## Game Loop Overview

The main loop runs until all states are guessed or the player exits:

1. Prompt the user for a state name
2. Normalize input (`.title()`)
3. Validate against known state names
4. Render correct guesses on the map
5. Track guessed states
6. Exit gracefully when requested

---

## Data & Coordinates

State positions are loaded from `50_states.csv`, which contains:

- `state` — state name
- `x`, `y` — Turtle screen coordinates for label placement

This allows accurate positioning of each state name on the map.

---

## Output: `states_to_learn.csv`

When the game ends, a file named `states_to_learn.csv` is generated containing all states that were **not guessed**.  
This can be reused for:

- Study lists
- Flashcards
- Follow-up quizzes

---

## Credits

Educational U.S. States guessing game built with Python Turtle and Pandas.
