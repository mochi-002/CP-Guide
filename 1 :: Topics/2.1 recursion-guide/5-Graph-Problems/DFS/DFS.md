```cpp
#include <iostream>
#include <vector>
using namespace std;

void dfs(int node, vector<vector<int>>& graph, vector<bool>& visited) {
    visited[node] = true;
    cout << node << " ";
    for (int neighbor : graph[node]) {
        if (!visited[neighbor]) {
            dfs(neighbor, graph, visited);
        }
    }
}

int main() {
    vector<vector<int>> graph = {{1,2}, {0,2,3}, {0,1}, {1}};
    vector<bool> visited(graph.size(), false);
    
    cout << "DFS starting from node 0: ";
    dfs(0, graph, visited);
    return 0;
}
```