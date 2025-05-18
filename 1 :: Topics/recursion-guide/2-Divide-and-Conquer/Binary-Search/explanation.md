# 🔍 Binary Search Algorithm

## ✅ Prerequisites

* The array must be **sorted** in ascending (or consistent) order.
* Elements must be **comparable** (e.g., numbers, strings).

---

## ⚙️ Algorithm Steps

1. Initialize `low = 0`, `high = n - 1`.
2. Compute mid-point:

   ```cpp
   mid = low + (high - low) / 2
   ```
3. If `arr[mid] == target`: return `mid`.
4. If `target < arr[mid]`: search the **left half** (`high = mid - 1`).
5. If `target > arr[mid]`: search the **right half** (`low = mid + 1`).

---

## 📊 Complexity Analysis

```math
Time Complexity: O(log n)
Space Complexity:
- O(1) for Iterative version
- O(log n) for Recursive version (due to call stack)
```

---

## 🧪 Example

**Input**:

```cpp
arr = [1, 3, 5, 7, 9]
target = 5
```

**Output**:

```
2  // Index of target (5)
```

---

## ⚠️ Edge Cases

* 🔹 Empty array (`[]`)
* 🔹 Target not found in array
* 🔹 Array contains **duplicate elements**

---
