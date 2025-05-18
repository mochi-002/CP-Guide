# Mutual Recursion

## What is Mutual Recursion?
**Mutual recursion** occurs when two or more functions call each other recursively, creating a cyclic dependency.

## Structure
- Each function must define a **base case**
- Each recursive call should **progress toward termination**

## Example: Even/Odd Checker
```cpp
bool isEven(int n) {
    if (n == 0) return true;
    return isOdd(n - 1);
}

bool isOdd(int n) {
    if (n == 0) return false;
    return isEven(n - 1);
}
```

## Common Use Cases

* Parsing **grammar rules**
* Simulating **state machines**
* Modeling **alternating conditions** or behaviors

## Pitfalls

* **Infinite recursion** if base cases are not properly defined
* **Harder to debug** due to interdependent call flow

> **Tip**: Always ensure that all recursive paths lead toward a terminating condition.

