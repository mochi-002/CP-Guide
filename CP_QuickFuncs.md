# CP Guide: CP Functions Cheatsheet 🚀

# Practical Tricks
## Bit Manipulation
### Check if a number is a power of 2
```cpp
bool isPowerOfTwo(int x) {
    return x && (!(x & (x - 1)));
}
```

### Count set bits (Brian Kernighan’s Algorithm)
```cpp
int countSetBits(int n) {
    int count = 0;
    while (n) {
        n &= (n - 1);
        count++;
    }
    return count;
}
```

### Get rightmost set bit
```cpp
int rightmostSetBit(int x) {
    return x & (-x);
}
```

### Swap two numbers without temporary variable
```cpp
void swap(int &a, int &b) {
    a ^= b;
    b ^= a;
    a ^= b;
}
```

## Number Theory
### Greatest Common Divisor (GCD)
```cpp
int gcd(int a, int b) {
    return b == 0 ? a : gcd(b, a % b);
}
```

### Sieve of Eratosthenes (Prime Numbers)
```cpp
vector<bool> sieve(int n) {
    vector<bool> is_prime(n+1, true);
    is_prime[0] = is_prime[1] = false;
    for (int i = 2; i*i <= n; i++) {
        if (is_prime[i]) {
            for (int j = i*i; j <= n; j += i) {
                is_prime[j] = false;
            }
        }
    }
    return is_prime;
}
```

## Combinatorics
### Factorial with Modulo
```cpp
const int MOD = 1e9+7;
vector<long long> fact(1e6+5, 1);

void precompute_factorials() {
    for (int i = 1; i <= 1e6; i++) {
        fact[i] = (fact[i-1] * i) % MOD;
    }
}
```

### Combination (nCr) "Without Overflow"
```cpp
const int MOD = 1e9+7;
vector<long long> fact, inv_fact;

long long binpow(long long a, long long b, long long mod) {
    a %= mod;
    long long res = 1;
    while (b > 0) {
        if (b & 1) res = (res * a) % mod;
        a = (a * a) % mod;
        b >>= 1;
    }
    return res;
}

void precompute(int n) {
    fact.resize(n+1);
    inv_fact.resize(n+1);
    fact[0] = 1;
    for (int i = 1; i <= n; i++) {
        fact[i] = (fact[i-1] * i) % MOD;
    }
    inv_fact[n] = binpow(fact[n], MOD-2, MOD);
    for (int i = n-1; i >= 0; i--) {
        inv_fact[i] = (inv_fact[i+1] * (i+1)) % MOD;
    }
}

// O(1) query - requires precompute(n) first
long long nCr(int n, int r) {
    if (r < 0 || r > n) return 0;
    return (fact[n] * inv_fact[r] % MOD) * inv_fact[n-r] % MOD;
}

// O(r) query - works without precomputation
long long nCr_mod(int n, int r) {
    if (r < 0 || r > n) return 0;
    r = min(r, n - r);
    long long res = 1;
    for (int i = 1; i <= r; i++) {
        res = res * (n - r + i) % MOD;
        res = res * binpow(i, MOD-2, MOD) % MOD;
    }
    return res;
}
```

## Geometry
### Distance between two points
```cpp
double distance(double x1, double y1, double x2, double y2) {
    return sqrt((x2-x1)*(x2-x1) + (y2-y1)*(y2-y1));
}
```
## String Manipulation
### Check if string is palindrome

```cpp
bool isPalindrome(const string &s) {
    int n = s.length();
    for (int i = 0; i < n/2; i++) {
        if (s[i] != s[n-1-i]) return false;
    }
    return true;
}
```
## Graph Algorithms
## Dijkstra's Shortest Path
```cpp
vector<int> dijkstra(vector<vector<pair<int, int>>> &graph, int start) {
    int n = graph.size();
    vector<int> dist(n, INT_MAX);
    priority_queue<pair<int, int>, vector<pair<int, int>>, greater<pair<int, int>>> pq;
    dist[start] = 0;
    pq.push({0, start});
    
    while (!pq.empty()) {
        auto [d, u] = pq.top();
        pq.pop();
        if (d > dist[u]) continue;
        for (auto &[v, w] : graph[u]) {
            if (dist[v] > dist[u] + w) {
                dist[v] = dist[u] + w;
                pq.push({dist[v], v});
            }
        }
    }
    return dist;
}
```

### Union-Find (Disjoint Set Union)
```cpp
struct DSU {
    vector<int> parent, size;
    
    DSU(int n) {
        parent.resize(n);
        size.resize(n, 1);
        iota(parent.begin(), parent.end(), 0);
    }
    
    int find(int x) {
        if (parent[x] != x) parent[x] = find(parent[x]);
        return parent[x];
    }
    
    bool unite(int x, int y) {
        x = find(x);
        y = find(y);
        if (x == y) return false;
        if (size[x] < size[y]) swap(x, y);
        parent[y] = x;
        size[x] += size[y];
        return true;
    }
};
```
