```cpp
#include <iostream>
using namespace std;

// Iterative function to calculate factorial
int factorial(int n) {
    int result = 1;
    // Multiply from 1 to n
    for (int i = 1; i <= n; i++) {
        result *= i;
    }
    return result;
}

int main() {
    int num = 5;
    cout << "Factorial of " << num << " is: " << factorial(num) << endl;
    return 0;
}
```