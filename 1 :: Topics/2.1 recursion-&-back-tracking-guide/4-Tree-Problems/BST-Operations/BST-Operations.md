```cpp#include <iostream>
using namespace std;

struct Node {
    int data;
    Node *left, *right;
    Node(int val) : data(val), left(nullptr), right(nullptr) {}
};

// Insert a node in BST
Node* insert(Node* root, int val) {
    if (!root) return new Node(val);
    if (val < root->data) 
        root->left = insert(root->left, val);
    else 
        root->right = insert(root->right, val);
    return root;
}

// Search a value in BST
bool search(Node* root, int val) {
    if (!root) return false;
    if (root->data == val) return true;
    return (val < root->data) ? search(root->left, val) : search(root->right, val);
}

int main() {
    Node* root = nullptr;
    root = insert(root, 5);
    insert(root, 3);
    insert(root, 7);
    
    cout << "Search 4: " << (search(root, 4) ? "Found" : "Not found") << endl;
    return 0;
}
```