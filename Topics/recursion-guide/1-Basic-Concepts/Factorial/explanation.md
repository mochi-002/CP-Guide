# 📘 Factorial Using Recursion

## 📐 Mathematical Definition

The **factorial** of a non-negative integer `n` is the product of all positive integers less than or equal to `n`:

```math
n! = n \times (n-1) \times (n-2) \times \dots \times 1
```

## 🧠 Recursive Definition

The factorial function can be defined recursively as:

* **Base Case**:

  * `0! = 1`
  * `1! = 1`

* **Recursive Case**:

  * `n! = n × (n-1)!`

## ⚙️ Complexity Analysis

| Approach  | Time Complexity | Space Complexity         |
| --------- | --------------- | ------------------------ |
| Recursive | O(n)            | O(n) (due to call stack) |
| Iterative | O(n)            | O(1)                     |

## 🧮 Example Calculation

```math
5! = 5 × 4 × 3 × 2 × 1 = 120
```

---
