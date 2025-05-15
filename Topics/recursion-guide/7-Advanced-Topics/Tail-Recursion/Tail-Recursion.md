```cpp
#include <iostream>
using namespace std;

// Tail-recursive factorial
int fact(int n, int acc = 1) {
    return (n == 0) ? acc : fact(n-1, n*acc);
}

int main() {
    cout << "5! = " << fact(5) << endl;
    return 0;
}
```