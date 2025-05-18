
# Binary Tree Traversals

## Overview
Traversal refers to visiting all the nodes in a binary tree in a specific order. There are three primary depth-first traversal methods.

## Types of Traversal

### 1. Pre-order Traversal (Root → Left → Right)
- Visit the root first, then left subtree, then right subtree
- **Use case**: Copying trees, prefix notation of expression trees

### 2. In-order Traversal (Left → Root → Right)
- Visit the left subtree, then root, then right subtree
- **Use case**: Retrieves elements in **sorted order** for Binary Search Trees (BST)

### 3. Post-order Traversal (Left → Right → Root)
- Visit the left subtree, then right subtree, then root
- **Use case**: Deleting nodes, postfix expression generation

## Example Tree
```

```
    1
   / \
  2   3

- **Pre-order**: [1, 2, 3]  
- **In-order**: [2, 1, 3]  
- **Post-order**: [2, 3, 1]

## Complexity Analysis

| Metric       | Value           | Notes                     |
|--------------|------------------|---------------------------|
| Time         | O(n)             | Each node visited once    |
| Space        | O(h)             | h = tree height (recursive stack) |

> In worst-case (skewed tree), space becomes **O(n)**
