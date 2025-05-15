### 🧾 **Cheatsheet.md**

A compact, go-to reference for algorithm patterns, complexities, and common formulas.

````markdown
# 🧾 Algorithms & DS Cheatsheet

## Time Complexities
| Algorithm      | Time Complexity |
|----------------|------------------|
| Binary Search  | O(log n)         |
| Merge Sort     | O(n log n)       |
| Dijkstra's     | O(E + V log V)   |

## Recursion Templates
```cpp
// Backtracking template
void backtrack(params) {
    if (base_case) return;
    for (option in options) {
        makeMove();
        backtrack(next);
        undoMove();
    }
}
````

## Common Patterns

* Sliding Window
* Two Pointers
* Dynamic Programming: Memoization & Tabulation

````
