# CP Guide: Competitive Programming Tips & Tricks 🚀

## ⚡ Faster Built-in Functions (GCC)

### Bit Manipulation
```cpp
// Count set bits (1s) in binary representation - O(1)
__builtin_popcount(x);          // for int
__builtin_popcountll(x);        // for long long

// Count leading/trailing zeros - O(1)
__builtin_clz(x);               // Count Leading Zeros (undefined for x=0)
__builtin_ctz(x);               // Count Trailing Zeros (undefined for x=0)

// Check parity (even/odd number of 1s)
__builtin_parity(x);            // Returns 1 if odd, 0 if even
```

### Math Utilities
```cpp
// Find most significant set bit (MSB)
int msb = 31 - __builtin_clz(x);  // Undefined for x=0

// Check if x is power of 2
bool is_pow2 = (x && !(x & (x - 1)));

// Fast log2 (integer)
int log2_floor = 31 - __builtin_clz(x);
```

### C++ Speed Boosts
```cpp
// Disable sync with C streams (2-3x faster)
ios_base::sync_with_stdio(false);
cin.tie(nullptr);

// Use '\n' instead of endl (avoids buffer flush)
cout << '\n';

// Reserve vector capacity to avoid reallocation
vector<int> v;
v.reserve(size_os_vector);  // Pre-allocate for 1M elements
```

### STL Shortcuts
```cpp
// Sum all elements in a container
int total = accumulate(v.begin(), v.end(), x);

// Find first element satisfying condition
auto it = find_if(v.begin(), v.end(), [](int x){ return x > 5; });

// Count occurrences
int cnt = count(v.begin(), v.end(), x);
```

### Some other STLs 
```cpp
// Ordered Set
#include <ext/pb_ds/assoc_container.hpp>
#include <ext/pb_ds/tree_policy.hpp>
using namespace __gnu_pbds;

template<typename T>
using ordered_set = tree<T, null_type, less<T>, rb_tree_tag,
                      tree_order_statistics_node_update>;

/* 
   Features:
   - Insert/erase in O(log n)
   - Find kth element in O(log n)
   - Count elements < X in O(log n)
*/
```
```cpp
// Ordered Multi Set
#include<ext/pb_ds/tree_policy.hpp>
#include<ext/pb_ds/assoc_container.hpp>
using namespace __gnu_pbds;
template<typename T>
using ordered_multiset = tree<T, null_type, less_equal<T>, rb_tree_tag,
                           tree_order_statistics_node_update>;
```
