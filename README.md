# SLE-3: Architectural Design (Full C4 Model) - 8-Puzzle Solver System

**Course:** 02AML204 - Introduction to Artificial Intelligence
**Name:** Pranjal Vijay Mane | **PRN:** 25UAM096 | **Division:** B

## Project Overview
This repository documents the architecture of an **8-Puzzle Solver System (Empirical Search Engine)** using the **C4 model**. The system solves the classic 8-Puzzle with two search strategies:
- **BFS** (uninformed search)
- **A\*** (informed search with the Manhattan Distance heuristic)

It takes a 3x3 starting board, searches for the shortest sequence of moves to the goal state `(1, 2, 3, 4, 5, 6, 7, 8, 0)`, and reports the solution path with profiling metrics (execution time and nodes expanded).

## Objective
To design and document the software architecture of the solver at four levels of abstraction (Context, Container, Component, Code), and to explain the design decisions behind it.

## C4 Model Summary

| Level | Diagram | Description |
|---|---|---|
| 1 | Context | The User / Operator gives an initial board to the 8-Puzzle Solver System and receives the solution path and profiling results |
| 2 | Container | Input Module, Search Engine, Heuristic Calculator, Memory State (Visited Set), Output Module |
| 3 | Component | Inside the Search Engine: Frontier Manager, Goal Test Evaluator, Neighbor Generator, Path Reconstructor |
| 4 | Code | `Node`, `get_neighbors`, `manhattan_distance`, `bfs`, `astar`, `reconstruct_path` |

### Containers
- **Input Module:** parses, validates and initializes the start and goal states.
- **Search Engine:** runs the chosen algorithm (BFS or A*).
- **Heuristic Calculator:** computes Manhattan Distance values for A*.
- **Memory State (Visited Set):** tracks explored states and best g-scores to avoid loops and repeated work.
- **Output Module:** formats the solution path, node counts and timings.

### Components (Search Engine)
- **Frontier Manager:** `deque` for BFS, `heapq` priority queue for A*.
- **Goal Test Evaluator:** checks whether a popped state equals the goal.
- **Neighbor Generator:** generates valid blank-tile moves (Up, Down, Left, Right).
- **Path Reconstructor:** follows parent pointers back from the goal to build the move sequence.

### Code Level
- `class Node` - board tuple, parent pointer, step cost `g`, total cost `f`
- `get_neighbors(state)` - generates adjacent board states
- `manhattan_distance(state)` - heuristic function
- `bfs(start, goal)` - Breadth-First Search using a FIFO queue
- `astar(start, goal)` - A* search ordered by `f(n) = g(n) + h(n)`
- `reconstruct_path(parent, state)` - builds the step-by-step solution

## Key Design Decisions
- **Decoupled search logic and heuristics:** heuristics can be swapped without changing the core search code.
- **Immutable tuples for states:** 1D tuples give O(1) set lookups for fast duplicate pruning.
- **Modular I/O separation:** input and profiling output are kept apart from the search logic, which keeps it simple to test.

## Repository Contents
- `sleai.py` - Python implementation of BFS and A* for the 8-Puzzle
- `SLE3_Pranjal-Vijay-Mane.pdf` - SLE-3 report with all four C4 diagrams and explanations
- `README.md` - this file

## How to Run
```bash
python sleai.py
```
Requires Python 3. The program prints the solution length, average time and nodes expanded for both algorithms.

## Tools Used
- Python 3
- draw.io (C4 diagrams)

## AI Contribution
- **AI tools used:** Claude, Gemini
- **AI helped with:** structuring the C4 levels, refining component descriptions, and formatting text.
- **My own work:** designed the component boundaries, mapped Python classes and functions to C4 levels, created the diagrams on draw.io, and wrote the design rationale.
