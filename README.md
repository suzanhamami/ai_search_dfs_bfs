# 🧠 AI Grid Search (BFS & DFS)

This project generates a random 12×12 grid environment and solves it using Breadth-First Search (BFS) and Depth-First Search (DFS) under specific movement constraints.

---

## 🚀 Overview

Each run creates a new grid containing:

* Empty cells (`.`)
* Mountains (`M`)
* Barriers (`X`) – cannot be crossed
* Start (`S`)
* Goal (`G`)
* Destinations (`D`) – must be visited before reaching the goal

The agent (robot) must:

> Start at `S`, visit all `D` cells, and only then reach `G`.

---

## 🧩 State Representation

Each state is defined as:

```
(row, col, visited_destinations)
```

* `row, col`: current position of the agent
* `visited_destinations`: set of visited destination cells (`D`), stored as a `frozenset`

---

## ⚙️ Algorithms Implemented

### Breadth-First Search (BFS)

* Explores the grid level by level
* Guarantees the shortest path in terms of number of steps

### Depth-First Search (DFS)

* Explores paths deeply before backtracking
* Does not guarantee the shortest path

---

## 🚧 Movement Rules

* The agent can move:

  * Up, Down, Left, Right
* Cannot move outside the grid
* Cannot move into barriers (`X`)
* Cannot enter the goal (`G`) unless all destinations (`D`) are visited

---

## 🎲 Grid Generation

The grid is randomly generated each run with fixed counts:

| Element          | Count           |
| ---------------- | --------------- |
| Mountains (M)    | 39              |
| Barriers (X)     | 9               |
| Start (S)        | 1               |
| Goal (G)         | 1               |
| Destinations (D) | 3               |
| Empty (.)        | Remaining cells |

Generation steps:

1. Create a list with the required number of each element
2. Shuffle the list randomly
3. Reshape it into a 12×12 grid

---

## 📌 Notes

* Some generated grids may be unsolvable due to random placement
* BFS and DFS operate based on valid movement and constraints only

---

## 🖥 Output

The program prints:

* The generated grid
* Start, goal, and destination positions
* Step-by-step solution path including:

  * Move direction
  * Current position
  * Visited destinations

---

## ▶️ How to Run

```bash
python puzzle.py
```

---

## 🔧 Possible Improvements

* Ensure always-solvable grid generation
* Visualize the path on the grid
* Track performance metrics (e.g., nodes explored)

---

## 👨‍💻 Authors
Suzan Hamami
Louay Arnaba Khordaji
