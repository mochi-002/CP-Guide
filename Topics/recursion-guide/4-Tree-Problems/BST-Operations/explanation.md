# Binary Search Tree (BST) Operations

## Definition
A Binary Search Tree (BST) is a binary tree where each node follows:
- Left child ≤ Node
- Node ≤ Right child

## Core Operations
### 1. Insertion
- Traverse left or right based on value
- Place new node at appropriate null spot
- Time: O(h), where h = height

### 2. Search
- Similar logic as insertion
- Return node if found, else null

### 3. Deletion (Not shown in code)
- Three cases:
  - Node with no child
  - Node with one child
  - Node with two children

## Recursive Pattern
1. **Base Case**: If node is null → return
2. **Recursive Step**: Compare & move left/right

## Complexity Analysis

| Operation | Avg Time | Worst Case |
|-----------|----------|------------|
| Insert    | O(log n) | O(n)       |
| Search    | O(log n) | O(n)       |
| Delete    | O(log n) | O(n)       |

> **Note**: Worst case occurs in skewed trees.
