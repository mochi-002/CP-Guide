# 🧠 Memoization vs Tabulation

Dynamic Programming (DP) can be implemented in two main styles:

---

## 🔝 Memoization (Top-Down)

```python
memo = {}

def fib(n):
    if n in memo:
        return memo[n]
    if n <= 1:
        return n
    memo[n] = fib(n - 1) + fib(n - 2)
    return memo[n]
```

* Recursively solves subproblems.
* Caches results to avoid recomputation.

---

## 🔽 Tabulation (Bottom-Up)

```python
def fib(n):
    dp = [0, 1]
    for i in range(2, n + 1):
        dp.append(dp[i - 1] + dp[i - 2])
    return dp[n]
```

* Iteratively builds the solution from the base cases.
* No recursion, just loops and storage.

---

## 📊 Comparison Table

| Feature     | Memoization                 | Tabulation        |
| ----------- | --------------------------- | ----------------- |
| Approach    | Top-down                    | Bottom-up         |
| Speed       | Slower (recursion overhead) | Faster            |
| Space       | O(n) (call stack + memo)    | O(n) (table only) |
| Readability | More intuitive              | More systematic   |

---
