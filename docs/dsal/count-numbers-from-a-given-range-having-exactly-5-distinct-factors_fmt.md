# 从给定范围内计数恰好有5个不同因子的数字

> 原文：[https://www.geeksforgeeks.org/count-numbers-from-a-given-range-having-exactly-5-distinct-factors/](https://www.geeksforgeeks.org/count-numbers-from-a-given-range-having-exactly-5-distinct-factors/)

给定两个整数 `L` 和 `R`，任务是从范围 `[L, R]` 中计算恰好具有 **5** 个不同正因子的数字的个数。

## 示例

**输入：** `L = 1`, `R = 100`
**输出：** `2`
**说明：** 在范围 `[1, 100]` 内，仅有两个数字恰好有 5 个不同的因子，它们是 16 和 81。
16 的因子是 `{1, 2, 4, 8, 16}`。
81 的因子是 `{1, 3, 9, 27, 81}`。

**输入：** `L = 1`, `R = 100`
**输出：** `2`

## 天真法

解决这个问题最简单的方法是遍历范围 `[L, R]`，对每一个数字统计其因子个数。如果因子计数等于 **5**，则将计数器增加 **1**。

- **时间复杂度：** `(R – L) × √N`
- **辅助空间：** `O(1)`

## 高效方法

为了优化上述方法，需要对恰好具有 5 个因子的数字进行以下观察。

> 设一个数的素数分解为 `p₁^a₁ × p₂^a₂ × … × pₙ^aₙ`。
> 那么该数的因子个数可以表示为 `(a₁ + 1) × (a₂ + 1) × … × (aₙ + 1)`。
> 由于这个乘积必须等于 **5**（是一个[质数](https://www.geeksforgeeks.org/prime-numbers/)），因此乘积中只能存在一个大于 1 的项。该项必须等于 5。
> 因此，如果 `aᵢ + 1 = 5`，则 `aᵢ = 4`。

按照以下步骤解决问题：

- 所需计数是范围内包含 `p⁴` 作为因子的数字个数，其中 **p** 是一个质数。
- 为了高效计算大范围（如 `[1, 10¹⁸]`）内的 `p⁴`，思路是使用[厄拉多塞筛](https://www.geeksforgeeks.org/sieve-of-eratosthenes/)来存储所有直到 `10⁴.⁵` 的质数。

下面是上述方法的实现：

### C++14

```cpp
// C++ Program to implement
// the above approach

#include <bits/stdc++.h>
using namespace std;

const int N = 2e5;

// Stores all prime numbers
// up to 2 * 10^5
vector<long long> prime;

// Function to generate all prime
// numbers up to 2 * 10 ^ 5 using
// Sieve of Eratosthenes
void Sieve()
{
    prime.clear();
    vector<bool> p(N + 1, true);

    // Mark 0 and 1 as non-prime
    p[0] = p[1] = false;

    for (int i = 2; i * i <= N; i++) {

        // If i is prime
        if (p[i] == true) {

            // Mark all its factors as non-prime
            for (int j = i * i; j <= N; j += i) {
                p[j] = false;
            }
        }
    }

    for (int i = 1; i < N; i++) {

        // If current number is prime
        if (p[i]) {

            // Store the prime
            prime.push_back(1LL * pow(i, 4));
        }
    }
}

// Function to count numbers in the
// range [L, R] having exactly 5 factors
void countNumbers(long long int L,
                  long long int R)
{

    // Stores the required count
    int Count = 0;

    for (int p : prime) {

        if (p >= L && p <= R) {
            Count++;
        }
    }
    cout << Count << endl;
}

// Driver Code
int main()
{
    long long L = 16, R = 85000;

    Sieve();

    countNumbers(L, R);

    return 0;
}
```

### Java

```java
// Java Program to implement
// the above approach
import java.util.*;
class GFG
{
  static int N = 200000;

  // Stores all prime numbers
  // up to 2 * 10^5
  static int prime[] = new int [20000];
  static int index = 0;

  // Function to generate all prime
  // numbers up to 2 * 10 ^ 5 using
  // Sieve of Eratosthenes
  static void Sieve()
  {
    index = 0;
    int p[] = new int [N + 1];
    for(int i = 0; i <= N; i++)
    {
      p[i] = 1;
    }

    // Mark 0 and 1 as non-prime
    p[0] = p[1] = 0;
    for (int i = 2; i * i <= N; i++)
    {

      // If i is prime
      if (p[i] == 1)
      {

        // Mark all its factors as non-prime
        for (int j = i * i; j <= N; j += i)
        {
          p[j] = 0;
        }
      }
    }
    for (int i = 1; i < N; i++)
    {

      // If current number is prime
      if (p[i] == 1)
      {

        // Store the prime
        prime[index++] = (int)(Math.pow(i, 4));
      }
    }
  }

  // Function to count numbers in the
  // range [L, R] having exactly 5 factors
  static void countNumbers(int L,int R)
  {

    // Stores the required count
    int Count = 0;
    for(int i = 0; i < index; i++)
    {
      int p = prime[i];
      if (p >= L && p <= R)
      {
        Count++;
      }
    }
    System.out.println(Count);
  }

  // Driver Code
  public static void main(String[] args)
  {
    int L = 16, R = 85000;
    Sieve();
    countNumbers(L, R);
  }
}

// This code is contributed by amreshkumar3.
```

### Python 3

```python
# Python3 implementation of
# the above approach
N = 2 * 100000

# Stores all prime numbers
# up to 2 * 10^5
prime = [0] * N

# Function to generate all prime
# numbers up to 2 * 10 ^ 5 using
# Sieve of Eratosthenes
def Sieve() :
    p = [True] * (N + 1)

    # Mark 0 and 1 as non-prime
    p[0] = p[1] = False
    i = 2
    while(i * i <= N) :

        # If i is prime
        if (p[i] == True) :

            # Mark all its factors as non-prime
            for j in range(i * i, N, i):
                p[j] = False    
        i += 1
    for i in range(N):

        # If current number is prime
        if (p[i] != False) :

            # Store the prime
            prime.append(pow(i, 4))

# Function to count numbers in the
# range [L, R] having exactly 5 factors
def countNumbers(L, R) :

    # Stores the required count
    Count = 0
    for p in prime :
        if (p >= L and p <= R) :
            Count += 1
    print(Count)

# Driver Code
L = 16
R = 85000
Sieve()
countNumbers(L, R)

# This code is contributed by code_hunt.
```

### C#

```csharp
// C# Program to implement
// the above approach
using System;
class GFG
{
  static int N = 200000;

  // Stores all prime numbers
  // up to 2 * 10^5
  static int []prime = new int [20000];
  static int index = 0;

  // Function to generate all prime
  // numbers up to 2 * 10 ^ 5 using
  // Sieve of Eratosthenes
  static void Sieve()
  {
    index = 0;
    int []p = new int [N + 1];
    for(int i = 0; i <= N; i++)
    {
      p[i] = 1;
    }

    // Mark 0 and 1 as non-prime
    p[0] = p[1] = 0;
    for (int i = 2; i * i <= N; i++)
    {

      // If i is prime
      if (p[i] == 1)
      {

        // Mark all its factors as non-prime
        for (int j = i * i; j <= N; j += i)
        {
          p[j] = 0;
        }
      }
    }
    for (int i = 1; i < N; i++)
    {

      // If current number is prime
      if (p[i] == 1)
      {

        // Store the prime
        prime[index++] = (int)(Math.Pow(i, 4));
      }
    }
  }

  // Function to count numbers in the
  // range [L, R] having exactly 5 factors
  static void countNumbers(int L,int R)
  {

    // Stores the required count
    int Count = 0;
    for(int i = 0; i < index; i++)
    {
      int p = prime[i];
      if (p >= L && p <= R)
      {
        Count++;
      }
    }
    Console.WriteLine(Count);
  }

  // Driver Code
  public static void Main(String[] args)
  {
    int L = 16, R = 85000;
    Sieve();
    countNumbers(L, R);
  }
}

// This code is contributed by shikhasingrajput
```

### JavaScript

```javascript
<script>
// javascript program of the above approach

let N = 200000;

  // Stores all prime numbers
  // up to 2 * 10^5
  let prime = new Array(20000).fill(0);
  let index = 0;

  // Function to generate all prime
  // numbers up to 2 * 10 ^ 5 using
  // Sieve of Eratosthenes
  function Sieve()
  {
    index = 0;
    let p = new Array (N + 1).fill(0);
    for(let i = 0; i <= N; i++)
    {
      p[i] = 1;
    }

    // Mark 0 and 1 as non-prime
    p[0] = p[1] = 0;
    for (let i = 2; i * i <= N; i++)
    {

      // If i is prime
      if (p[i] == 1)
      {

        // Mark all its factors as non-prime
        for (let j = i * i; j <= N; j += i)
        {
          p[j] = 0;
        }
      }
    }
    for (let i = 1; i < N; i++)
    {

      // If current number is prime
      if (p[i] == 1)
      {

        // Store the prime
        prime[index++] = (Math.pow(i, 4));
      }
    }
  }

  // Function to count numbers in the
  // range [L, R] having exactly 5 factors
  function countNumbers(L, R)
  {

    // Stores the required count
    let Count = 0;
    for(let i = 0; i < index; i++)
    {
      let p = prime[i];
      if (p >= L && p <= R)
      {
        Count++;
      }
    }
    document.write(Count);
  }

    // Driver Code

    let L = 16, R = 85000;
    Sieve();
    countNumbers(L, R);

</script>
```

**输出：**

```
2
```

- **时间复杂度：** `O(N * log(log(N)))`
- **辅助空间：** `O(N)`