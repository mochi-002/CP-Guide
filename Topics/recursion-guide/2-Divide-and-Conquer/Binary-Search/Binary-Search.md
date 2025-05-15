```cpp
#include <iostream>
#include <vector>
using namespace std;

// Iterative implementation
int binarySearch(const vector<int>& arr, int target) {
    int low = 0, high = arr.size() - 1;
    
    while (low <= high) {
        int mid = low + (high - low)/2;
        
        if (arr[mid] == target) return mid;
        if (target < arr[mid]) high = mid - 1;
        else low = mid + 1;
    }
    return -1;
}

int main() {
    vector<int> arr = {1,3,5,7,9};
    int target = 5;
    int result = binarySearch(arr, target);
    
    cout << "Target found at index: " << result << endl;
    return 0;
}
```