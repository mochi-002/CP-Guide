```cpp
#include <iostream>
#include <vector>
using namespace std;

bool hasCycle(int node, vector<vector<int>>& graph, vector<bool>& visited, int parent) {
    visited[node] = true;
    for (int neighbor : graph[node]) {
        if (!visited[neighbor]) {
            if (hasCycle(neighbor, graph, visited, node)) 
                return true;
        } else if (neighbor != parent) {
            return true;
        }
    }
    return false;
}

int main() {
    vector<vector<int>> graph = {{1}, {0,2}, {1,3}, {2}};
    vector<bool> visited(graph.size(), false);
    
    cout << "Graph has cycle: " << (hasCycle(0, graph, visited, -1) ? "Yes" : "No");
    return 0;
}
```