# Pong (with Turtle)

A simple, classic **Pong** clone built with Python’s built-in **turtle** graphics module.  
Two paddles face off, a ball bounces around the arena, and the scoreboard tracks who scores.

---

## Preview

- **Right paddle:** Arrow keys (↑ / ↓)
- **Left paddle:** `W` / `S`
- Ball speed **increases slightly** after every paddle hit
- Score updates automatically when the ball passes a paddle

---

## Features

- 2-player local controls (keyboard)
- Paddle movement with smooth screen updates (`tracer(0)`)
- Ball physics:
  - Bounces on top/bottom walls
  - Bounces on paddle collisions
  - Gets faster over time on successful hits
- Scoreboard with left/right scores
- Ball resets after a point is scored

---

**What each file does:**
- `main.py` — game loop, input bindings, collision checks, scoring logic
- `player.py` — paddle (player) class, moves up/down
- `ball.py` — ball class, movement + bounce + speed control
- `scoreboard.py` — scoring display and score tracking

---

## Requirements

- Python **3.x**
- No external packages needed (uses Python’s standard library)

> Note: `turtle` opens a GUI window, so it works best on a local machine.

---

## How to Run

1. Clone the repository:
   ```
   git clone <repo-url>
   cd <repo-folder>
2. Run
   ```
   python3 main.py

## Controls

| Player | Move Up | Move Down |
|--------|---------|-----------|
| Left Paddle | `W` | `S` |
| Right Paddle | `↑` | `↓` |

---

## Gameplay Rules

- The ball bounces off the top and bottom walls.
- When the ball hits a paddle, it:
  - Reverses horizontal direction
  - Slightly increases speed, making games progressively harder
- If the ball passes the right edge, the left player scores
- If the ball passes the left edge, the right player scores
- After each point:
  - The ball resets to the center
  - Speed is reset
  - Ball launches in the opposite direction

---

## Game Loop Overview

The main loop performs the following steps continuously:

1. Delay based on current ball speed
2. Update the screen manually (`tracer(0)`)
3. Move the ball
4. Check for:
   - Wall collisions
   - Paddle collisions
   - Scoring conditions

---

## Customization

You can tweak gameplay easily:

- Ball speed / difficulty
  - Ball.move_speed (lower = faster updates)
  - Ball.x_move / Ball.y_move (movement step per tick)
- Paddle speed
  - In Player.up() / Player.down(), change 20 to another value
- Window size
  - In main.py: screen.setup(width=800, height=600)

---

