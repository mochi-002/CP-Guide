```cpp
#include <iostream>
using namespace std;

bool isOdd(int n);
bool isEven(int n) {
    return (n == 0) ? true : isOdd(n-1);
}
bool isOdd(int n) {
    return (n == 0) ? false : isEven(n-1);
}

int main() {
    cout << "Is 5 even? " << isEven(5) << endl;
    return 0;
}
```