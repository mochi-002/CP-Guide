# 👑 N-Queens Problem

## 🧩 Problem Statement

Place **N** chess queens on an **N×N** board such that no two queens threaten each other (no two queens share the same row, column, or diagonal).

---

## 🔁 Approach: Backtracking

1. Place queens **row by row**.
2. For each row, try **all columns**.
3. If it's **safe**, place the queen and **recurse** to the next row.
4. If no safe position, **backtrack** and try a different configuration.

---

## 🛠️ Key Functions

* `isSafe(row, col)`: Checks for threats in column and both diagonals.
* `solveNQueens(row)`: Main recursive function using backtracking.

---

## 📊 Complexity Analysis

| Metric | Value | Explanation                            |
| ------ | ----- | -------------------------------------- |
| Time   | O(N!) | N choices in row 1, N-1 in row 2, etc. |
| Space  | O(N²) | To store the board configuration       |

---

## 🧪 Example (N = 4)

**Solution 1:**

```
. Q . .
. . . Q
Q . . .
. . Q .
```

**Solution 2:**

```
. . Q .
Q . . .
. . . Q
. Q . .
```

---

## 🚀 Optimization Tips

1. Use **bitmasking** to track columns and diagonals.
2. Exploit **symmetry** to reduce computation.
3. Replace board with 1D array (e.g., `queens[row] = col`) to save space.
---