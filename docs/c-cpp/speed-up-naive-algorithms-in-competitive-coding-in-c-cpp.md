# 借助 C/C++ 中的 Pragma 加速代码执行

> 原文:[https://www . geesforgeks . org/speed-up-native-algorithms-in-competitive-coding-in-c-CPP/](https://www.geeksforgeeks.org/speed-up-naive-algorithms-in-competitive-coding-in-c-cpp/)

一个[编译器](https://www.geeksforgeeks.org/introduction-of-compiler-design/)的首要目标是降低编译成本，让[调试](https://www.geeksforgeeks.org/software-engineering-debugging/)产生预期的结果。并非所有的[优化](https://www.geeksforgeeks.org/basic-code-optimizations-in-c/)都是由一个标志直接控制的，有时候我们需要显式声明标志来产生优化。默认情况下，优化被抑制。为了使用抑制优化，我们将使用[实用程序](https://www.geeksforgeeks.org/pragma-directive-in-c-c/)。

**未优化程序的例子:**让我们考虑一个例子来[计算 10000000](https://www.geeksforgeeks.org/sieve-of-eratosthenes/) 的素数。

下面是没有优化的代码:

## c++

```cpp
// C++ program to calculate the Prime
// Numbers upto 10000000 using Sieve
// of Eratosthenes with NO optimization

#include <cmath>
#include <iostream>
#include <vector>
#define N 10000005
using namespace std;

// Boolean array for Prime Number
vector<bool> prime(N, true);

// Sieve implemented to find Prime
// Number
void sieveOfEratosthenes()
{
    for (int i = 2; i <= sqrt(N); ++ i) {
        if (prime[i]) {
            for (int j = i * i; j <= N; j += i) {
                prime[j] = false;
            }
        }
    }
}

// Driver Code
int main()
{
    // Initialise clock to calculate
    // time required to execute without
    // optimization
    clock_t start, end;

    // Start clock
    start = clock();

    // Function call to find Prime Numbers
    sieveOfEratosthenes();

    // End clock
    end = clock();

    // Calculate the time difference
    double time_taken
        = double(end - start)
          / double(CLOCKS_PER_SEC);

    // Print the Calculated execution time
    cout << "Execution time: " << time_taken
         << " secs";

    return 0;
}
```

**输出:**

```cpp
Execution time: 0.592183 secs
```