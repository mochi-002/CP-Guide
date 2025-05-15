# Cycle Detection in Undirected Graphs

## Key Idea
Use DFS while tracking parent node:
- If a visited node is encountered and it’s not the parent → cycle exists

## Algorithm Steps
1. Start DFS from an unvisited node
2. Track visited nodes and parent
3. If a back edge is found → cycle detected

## Example
Graph: `0 — 1 — 2 — 3 — 2`
- Cycle found at node 2

## Complexity

| Metric   | Value     |
|----------|-----------|
| Time     | O(V + E)  |
| Space    | O(V)      |

> For directed graphs, use recursion stack or color tracking.
