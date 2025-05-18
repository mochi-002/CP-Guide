# Tail Recursion

## What is Tail Recursion?
A recursive function is **tail-recursive** if the recursive call is the **last operation** executed in the function—i.e., no computation occurs after the recursive call.

## Benefits
- Can be optimized to use **constant stack space**
- Helps avoid **stack overflow** in deep recursions

## Example
```cpp
int factorial(int n, int acc = 1) {
    return (n == 0) ? acc : factorial(n - 1, n * acc);
}
```

## Comparison

| Type             | Stack Usage         |
| ---------------- | ------------------- |
| Normal Recursion | O(n)                |
| Tail Recursion   | O(1) (if optimized) |

> **Note**: Tail Call Optimization (TCO) depends on the compiler and may not always be applied automatically.