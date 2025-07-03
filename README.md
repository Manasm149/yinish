
# 🕹️ Yinsh Game AI – Adversarial Search Project

## 📘 Overview

This project implements an AI agent to play the board game **Yinsh** using adversarial search algorithms like **Minimax** and **Alpha-Beta Pruning**. The AI operates in a sequential, deterministic, and adversarial setting, where strategic decision-making is key.

## 🎯 Objective

Each player starts with **M rings** (typically 5) on a hexagonal board of side **N** (typically 5). The goal is to be the first to **remove L rings** (usually 3). To remove a ring, the player must form a line of **K markers** (usually 5) of their own color.

## ♟️ Game Phases

### 1. **Ring Placement Phase**
- Players alternate placing their rings on empty cells.
- Each player places **M rings**.

### 2. **Main Game Phase**
On each turn, a player can:

- **Move a ring**:
  - It moves in a straight line.
  - Cannot jump over other rings.
  - Can jump over contiguous markers **once per move**.
  - All crossed markers **flip color** (black ↔ white).
  - Leaves a marker of the ring’s color on the starting position.

- **Remove markers and a ring**:
  - If you have a line of **5 continuous markers** (can be more), you can remove them by clicking both ends.
  - Then, you **must remove one of your rings** from the board.

## 🚫 Movement Restrictions
- A ring cannot cross another ring.
- A ring **must stop** at the first empty cell after crossing markers.
- Rings cannot zig-zag; they move in a straight direction only.

## 🏁 Win Conditions

A player wins by removing **L rings** first.

## ⚖️ Stalemate and Draws

If no legal moves remain:
- Player with more rings removed: **Stalemate Win**
- Player with fewer rings removed: **Stalemate Loss**
- Equal rings removed: **Draw**

## 📊 Performance Evaluation

Each match results in one of the following equivalence classes:
```
Win > Stalemate Win > Draw > Stalemate Loss > Loss
```

### Tie-breaker (within same class):
- Difference in number of markers on the board (you - opponent).

Each pair of players plays **2 matches**, switching who starts first.

## ⚙️ AI Features

- Implements **Minimax search** for move evaluation.
- Uses **Alpha-Beta pruning** for efficiency.
- Heuristic evaluation based on:
  - Number of removable marker lines
  - Mobility (legal moves available)
  - Board control (ring positions, marker influence)

## 🧠 Strategy Notes

- Don't rush to remove a marker line if it exposes your rings.
- Try setting up multiple threats (double lines).
- Defend by flipping opponent’s marker lines or blocking ring mobility.

---

> 🔗 *Make sure to check the official rules or visual demos to understand legal moves and toggling of markers during ring movement.*

