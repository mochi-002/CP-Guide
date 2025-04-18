# Math Tricks & Rules for Competitive Programming

```cpp
#pragma once
// This file contains essential math formulas optimized for CP
```

## 🔢 Basic Algebra
### Quadratic Formula
```cpp
// Solutions to ax² + bx + c = 0
vector<double> quadratic(double a, double b, double c) {
    double d = b*b - 4*a*c;
    if (d < 0) return {}; // No real roots
    d = sqrt(d);
    return {(-b - d)/(2*a), (-b + d)/(2*a)};
}

## 🔢 Bitwise-Number Theory Hybrid
### Addition ↔ XOR Relationship
```cpp
int sum_using_xor(int a, int b) {
    return (a ^ b) + 2*(a & b);  // a + b = (a ^ b) + 2*(a & b)
}
```
### Subtraction Equivalent
```cpp
int sub_using_xor(int a, int b) {
    return (a ^ b) - 2*(~a & b);  // a - b = (a ^ b) - 2*(~a & b)
}
```

## 📐 Geometry Shortcuts
### Lattice Points on Line Segment
```cpp
int count_lattice_points(int x1, int y1, int x2, int y2) {
    return gcd(abs(x2 - x1), abs(y2 - y1)) + 1;
}

// 3D Extension
int lattice_3d(int x1, int y1, int z1, int x2, int y2, int z2) {
    return gcd(gcd(abs(x2-x1), abs(y2-y1)), abs(z2-z1)) + 1;
}
```

## ⏱️ Modular Arithmetic
### Safe Modular Multiplication
```cpp
const int MOD = 1e9+7;
int mod_mul(int a, int b) {
    return (1LL * a * b) % MOD;
}
```
### Fast Exponentiation
```cpp
int mod_pow(int base, int exp) {
    int res = 1;
    while (exp > 0) {
        if (exp & 1) res = mod_mul(res, base);
        base = mod_mul(base, base);
        exp >>= 1;
    }
    return res;
}
```

## 🎲 Combinatorics
### Pascal's Triangle (nCr)
```cpp
vector<vector<int>> build_pascal(int max_n) {
    vector<vector<int>> C(max_n+1, vector<int>(max_n+1));
    for (int n = 0; n <= max_n; n++) {
        C[n][0] = C[n][n] = 1;
        for (int k = 1; k < n; k++)
            C[n][k] = C[n-1][k-1] + C[n-1][k];
    }
    return C;
}
```

### nCr Formula
```cpp
// the one handels big numbers is in CP QuickFuncs.md
C(n,k) = C(n-1,k) + C(n-1,k-1);
```

## 📊 Summation Formulas
### Arithmetic Series
```cpp
int sum_1_to_n(int n) {
    return n * (n + 1) / 2;
}

int sum_squares(int n) {
    return n * (n + 1) * (2 * n + 1) / 6;
}

int sum_cubes(int n) {
    int s = sum_1_to_n(n);
    return s * s;
}

int sum_quadratic(int n, int a, int b, int c) {
    return a * sum_squares(n) + b * sum_1_to_n(n) + c * n;
}
```

## 🔍 Divisibility Tricks
### Fast Checks
```cpp
bool is_even(int x) { return !(x & 1); }
```

## 🎯 Prime Number Tools
### Wilson's Theorem
```cpp
// for only p < 20
bool is_prime(int p) {
    if (p <= 1) return false;
    long long fact = 1;
    for (int i = 2; i < p; i++) 
        fact = (fact * i) % p;
    return fact == p - 1;
}
```
