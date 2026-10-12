# AI Contribution Log - SLE-3: Architectural Design (Full C4 Model)

**Name:** Pranjal Vijay Mane | **PRN:** 25UAM096 | **Division:** B
**Course:** 02AML204 - Introduction to Artificial Intelligence
**Project:** 8-Puzzle Solver System (Empirical Search Engine)
**Date:** 04-10-2026

---

## 1. AI Tools Used

| Tool | Purpose |
|---|---|
| Claude | Structuring the four C4 levels, suggesting how to organise the report, and improving the wording of explanations |
| Gemini | Refining component descriptions and improving the text layout |

AI was used only for documentation and structure. The architecture itself (what the modules are and how they connect) was decided by me, based on my own BFS and A* code from SLE-2.

---

## 2. AI-Generated Content

| Report Section | What AI Generated |
|---|---|
| Overall structure | Order and headings of the C4 levels (Context, Container, Component, Code) |
| System description | First draft of the short description of the 8-Puzzle Solver System |
| Context explanation | Wording of the 3-5 line explanation of the system boundary |
| Container explanations | First-draft sentences describing each container's role |
| Component explanations | First-draft sentences describing each Search Engine component |
| Formatting | Bullet formatting and text layout throughout the report |

---

## 3. My Own Work

| Area | What I Did |
|---|---|
| Architecture design | Decided the five containers: Input Module, Search Engine, Heuristic Calculator, Memory State (Visited Set), Output Module |
| Component boundaries | Decided that the Search Engine contains the Frontier Manager, Goal Test Evaluator, Neighbor Generator and Path Reconstructor |
| Code mapping | Mapped my Python code to Level 4: `Node`, `get_neighbors`, `manhattan_distance`, `bfs`, `astar`, `reconstruct_path` |
| Diagrams | Drew the Context, Container and Component diagrams myself on draw.io and chose the layout and arrows |
| Design decisions | Wrote the three design decisions: decoupled search and heuristics, immutable tuples for state tracking, modular I/O separation |
| Verification | Checked that each box in the diagrams matches a real part of my code, and that the descriptions are accurate |
| Final editing | Reviewed all AI-suggested text and edited it before including it in the report |

---

## 4. Issues Found in AI Output & Fixes

Keep only the issues that really happened and edit them in your own words.

| # | Issue Found | Fix Applied |
|---|---|---|
| 1 | [e.g. AI descriptions were generic and did not mention my actual structures, such as `deque` for BFS and `heapq` for A*] | [e.g. Rewrote the Frontier Manager description to name `deque` and `heapq`] |
| 2 | [e.g. AI suggested components or containers that do not exist in my code] | [e.g. Removed them so the diagrams match the real program] |
| 3 | [e.g. AI explanations were too long for the 3-5 line limit] | [e.g. Shortened them to the key points] |

---

## 5. How I Verified the AI Content

- Compared every container and component with my SLE-2 code (`sleai.py`) to make sure nothing was invented.
- Checked that the diagram arrows match the real data flow: Input Module -> Search Engine -> Output Module, with the Heuristic Calculator and Memory State supporting the Search Engine.
- Re-read each explanation and rewrote any sentence I could not explain in my own words.

---

## 6. Example Prompts Used (optional)

- [Paste 1-2 real prompts you gave to Claude or Gemini, e.g. "Help me structure a C4 model report for an 8-puzzle solver with BFS and A*."]

---

## 7. Declaration

I confirm that the architecture design, diagrams and design decisions in SLE-3 are my own work. AI tools were used only for structuring and wording support, and I understand and can explain everything submitted.
