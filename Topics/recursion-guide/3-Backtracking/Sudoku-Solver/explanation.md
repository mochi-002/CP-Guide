# 🔢 Sudoku Solver

## 🧩 Problem Statement

Fill a **9×9** grid so that:

* Each **row** contains digits 1–9 with no repetition.
* Each **column** contains digits 1–9 with no repetition.
* Each **3×3** subgrid contains digits 1–9 with no repetition.

---

## 🔁 Approach: Backtracking

1. Find the **next empty cell** (`.` or `0`).
2. Try placing digits **1–9**.
3. If **valid**, place digit and **recurse**.
4. If invalid or dead-end, **backtrack**.

---

## 🛠️ Key Functions

* `isValid(row, col, num)`: Checks row, column, and subgrid.
* `solveSudoku()`: Recursively solves the puzzle using backtracking.

---

## 📊 Complexity Analysis

| Metric | Value  | Explanation                          |
| ------ | ------ | ------------------------------------ |
| Time   | O(9^m) | `m` = number of empty cells          |
| Space  | O(1)   | In-place solution (no extra storage) |

---

## 🧪 Example Input

```
5 3 . | . 7 . | . . .
6 . . | 1 9 5 | . . .
. 9 8 | . . . | . 6 .
------+-------+------
8 . . | . 6 . | . . 3
4 . . | 8 . 3 | . . 1
7 . . | . 2 . | . . 6
------+-------+------
. 6 . | . . . | 2 8 .
. . . | 4 1 9 | . . 5
. . . | . 8 . | . 7 9
```

---

## 🚀 Optimization Tips

1. Use **MRV (Most Constrained Variable)** heuristic.
2. Precompute **possible values** for each cell.
3. Implement **Dancing Links (DLX)** for more advanced solving.
