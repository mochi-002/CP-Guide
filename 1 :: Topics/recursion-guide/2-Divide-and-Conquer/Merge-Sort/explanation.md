# 🧩 Merge Sort Algorithm

## ⚙️ How It Works

1. **Divide**: Recursively split the array into two halves until each subarray contains a single element.
2. **Conquer**: Recursively sort the subarrays.
3. **Combine**: Merge the sorted subarrays to produce the final sorted array.

---

## 📊 Complexity Analysis

```math
Time Complexity: O(n log n)   // Best, Average, and Worst Cases
Space Complexity: O(n)        // Auxiliary space for merging
```

---

## 🌟 Key Features

* ✅ **Stable sort** — maintains relative order of equal elements
* ✅ Efficient on **large datasets**
* ✅ Easily **parallelizable**

---

## 🧪 Example

**Input**:

```cpp
[38, 27, 43, 3, 9, 82, 10]
```

**Output**:

```
[3, 9, 10, 27, 38, 43, 82]
```

---

## ❓ When to Use?

* When **stability** is important
* Sorting **linked lists** (can be more space-efficient)
* When working with **large datasets** where predictable performance is required

---
