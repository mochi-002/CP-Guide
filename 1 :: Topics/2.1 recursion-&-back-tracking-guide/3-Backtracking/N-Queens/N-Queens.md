```cpp
#include <iostream>
#include <vector>
using namespace std;

void printBoard(const vector<string>& board) {
    for (const string& row : board) {
        cout << row << endl;
    }
    cout << endl;
}

bool isSafe(const vector<string>& board, int row, int col, int n) {
    // Check same column
    for (int i = 0; i < row; i++) {
        if (board[i][col] == 'Q') return false;
    }
    
    // Check upper left diagonal
    for (int i = row, j = col; i >= 0 && j >= 0; i--, j--) {
        if (board[i][j] == 'Q') return false;
    }
    
    // Check upper right diagonal
    for (int i = row, j = col; i >= 0 && j < n; i--, j++) {
        if (board[i][j] == 'Q') return false;
    }
    
    return true;
}

void solveNQueens(vector<string>& board, int row, int n) {
    if (row == n) {
        printBoard(board);
        return;
    }
    
    for (int col = 0; col < n; col++) {
        if (isSafe(board, row, col, n)) {
            board[row][col] = 'Q';  // Place queen
            solveNQueens(board, row + 1, n);
            board[row][col] = '.';  // Backtrack
        }
    }
}

int main() {
    int n = 4;  // Board size
    vector<string> board(n, string(n, '.'));
    solveNQueens(board, 0, n);
    return 0;
}
```