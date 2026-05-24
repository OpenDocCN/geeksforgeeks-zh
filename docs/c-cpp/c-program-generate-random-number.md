# C++ 程序生成随机数

> 原文:[https://www . geesforgeks . org/c-program-generate-random-number/](https://www.geeksforgeeks.org/c-program-generate-random-number/)

下面的实现是生成从 1 到给定极限的随机数。下面的函数产生类似于 [srand()](https://www.geeksforgeeks.org/rand-and-srand-in-ccpp/) 函数的行为。

先决条件:[c++ 中的随机头|集 1(生成器)](https://www.geeksforgeeks.org/random-header-c-set-1generators/)

```cpp
// C++ program to generate random number
#include <bits/stdc++.h>
using namespace std;

// Function with return random number from 1 to
// given limit
int randomNoGenerator(int limit)
{
    // uniformly-distributed integer random number
    // generator that produces non-deterministic
    // random numbers.
    random_device rd;

    // A Mersenne Twister pseudo-random generator
    // of 32-bit numbers with a state size of
    // 19937 bits.
    mt19937 gen(rd());

    // Uniform distribution
    uniform_int_distribution<> dis(1, limit);
    return dis(gen);
}

// Driver Code
int main()
{
    int limit = 100;
    cout << randomNoGenerator(limit) << endl;
    return 0;
}
```