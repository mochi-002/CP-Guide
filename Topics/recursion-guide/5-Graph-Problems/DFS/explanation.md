# Depth-First Search (DFS)

## Algorithm Steps
1. Mark current node as visited
2. Process the node (e.g., print/store)
3. Recursively visit unvisited neighbors

## Characteristics
- Uses implicit stack (recursion)
- Can be implemented iteratively

## Applications
- Finding connected components
- Topological sorting
- Solving mazes and puzzles

## Complexity

| Metric   | Value     |
|----------|-----------|
| Time     | O(V + E)  |
| Space    | O(V)      |

> **Tip**: Use iterative DFS to avoid stack overflow on large graphs.
