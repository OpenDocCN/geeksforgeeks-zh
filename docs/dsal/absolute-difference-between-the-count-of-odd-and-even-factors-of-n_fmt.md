# N 的奇偶因子计数的绝对差

> 原文: [https://www.geeksforgeeks.org/absolute-difference-between-the-count-of-odd-and-even-factors-of-n/](https://www.geeksforgeeks.org/absolute-difference-between-the-count-of-odd-and-even-factors-of-n/)

给定一个正整数 `N`，任务是求 `N` 的奇偶因子的计数的绝对差。

## 示例

**输入:** `N = 12`
**输出:** `2`
**说明:** 12 的偶因子为 `{2, 4, 6, 12}`。因此，计数为 4。
12 的奇数因子为 `{1, 3}`。因此，计数为 2。
因此，它们的计数之差为 `(4 - 2) = 2`。

**输入:** `N = 9`
**输出:** `3`

## 天真法

解决给定问题最简单的方法是求数 `N` 的所有除数，然后求 `N` 的奇数和偶数除数的计数的绝对差。

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`

## 有效方法

上述方法可以基于以下观察进行优化：

*   根据**唯一因子分解定理**，任何数都可以用素数幂的乘积来表示。因此，`N` 可以表示为：
    `N = P1^A1 * P2^A2 * P3^A3 * ... * PK^AK` (1 ≤ i ≤ K)
*   因此，因子总数 = `(A1 + 1) * (A2 + 1) * (A3 + 1) * ... * (AK + 1)`。这个数就是 `T`。
*   奇数因子的总数可以通过排除上述公式中的 2 的幂来计算。让这个计数为 `O`。
*   偶数因子的总数等于因子总数与奇数因子总数之差。

所以思路是利用厄拉多塞的筛求 `N` 的素因子分解中的素因子及其幂，打印出因子总数与奇数因子总数的两倍之差的值绝对值作为结果，即 `abs(T - 2 * O)`。

下面是上述方法的实现：

## C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to find the smallest prime
// factor of all the numbers using
// Sieve Of Eratosthenes
void sieveOfEratosthenes(int N, int s[])
{
    // Stores whether any number
    // is prime or not
    vector<bool> prime(N + 1, false);

    // Initialize smallest factor as
    // 2 for all the even numbers
    for (int i = 2; i <= N; i += 2)
        s[i] = 2;

    // Iterate over the range [3, N]
    for (int i = 3; i <= N; i += 2) {

        // If i is prime
        if (prime[i] == false) {

            s[i] = i;

            // Iterate all multiples of i
            for (int j = i; j * i <= N;
                 j += 2) {

                // i is the smallest
                // prime factor of i * j
                if (!prime[i * j]) {
                    prime[i * j] = true;
                    s[i * j] = i;
                }
            }
        }
    }
}

// Function to find the absolute
// difference between the count
// of odd and even factors of N
void findDifference(int N)
{
    // Stores the smallest
    // prime factor of i
    int s[N + 1];

    // Fill values in s[] using
    // sieve of eratosthenes
    sieveOfEratosthenes(N, s);

    // Stores the total number of
    // factors and the total number
    // of odd and even factors
    int total = 1, odd = 1, even = 0;

    // Store the current prime
    // factor of the number N
    int curr = s[N];

    // Store the power of
    // current prime factor
    int cnt = 1;

    // Loop while N is greater than 1
    while (N > 1) {
        N /= s[N];

        // If N also has smallest
        // prime factor as curr, then
        // increment cnt by 1
        if (curr == s[N]) {
            cnt++;
            continue;
        }

        // Update only total number
        // of factors if curr is 2
        if (curr == 2) {
            total = total * (cnt + 1);
        }

        // Update total number of
        // factors and total number
        // of odd factors
        else {
            total = total * (cnt + 1);
            odd = odd * (cnt + 1);
        }

        // Update current prime
        // factor as s[N] and
        // count as 1
        curr = s[N];
        cnt = 1;
    }

    // Calculate the number
    // of even factors
    even = total - odd;

    // Print the difference
    cout << abs(even - odd);
}

// Driver Code
int main()
{
    int N = 12;
    findDifference(N);

    return 0;
}
```

## Java

```java
// Java program for the above approach
import java.util.*;

class GFG{

// Function to find the smallest prime
// factor of all the numbers using
// Sieve Of Eratosthenes
static void sieveOfEratosthenes(int N, int s[])
{

    // Stores whether any number
    // is prime or not
    boolean []prime = new boolean[N + 1];

    // Initialize smallest factor as
    // 2 for all the even numbers
    for(int i = 2; i <= N; i += 2)
        s[i] = 2;

    // Iterate over the range [3, N]
    for(int i = 3; i <= N; i += 2)
    {

        // If i is prime
        if (prime[i] == false)
        {
            s[i] = i;

            // Iterate all multiples of i
            for(int j = i; j * i <= N; j += 2)
            {

                // i is the smallest
                // prime factor of i * j
                if (!prime[i * j])
                {
                    prime[i * j] = true;
                    s[i * j] = i;
                }
            }
        }
    }
}

// Function to find the absolute
// difference between the count
// of odd and even factors of N
static void findDifference(int N)
{

    // Stores the smallest
    // prime factor of i
    int []s = new int[N + 1];

    // Fill values in s[] using
    // sieve of eratosthenes
    sieveOfEratosthenes(N, s);

    // Stores the total number of
    // factors and the total number
    // of odd and even factors
    int total = 1, odd = 1, even = 0;

    // Store the current prime
    // factor of the number N
    int curr = s[N];

    // Store the power of
    // current prime factor
    int cnt = 1;

    // Loop while N is greater than 1
    while (N > 1)
    {
        N /= s[N];

        // If N also has smallest
        // prime factor as curr, then
        // increment cnt by 1
        if (curr == s[N])
        {
            cnt++;
            continue;
        }

        // Update only total number
        // of factors if curr is 2
        if (curr == 2)
        {
            total = total * (cnt + 1);
        }

        // Update total number of
        // factors and total number
        // of odd factors
        else
        {
            total = total * (cnt + 1);
            odd = odd * (cnt + 1);
        }

        // Update current prime
        // factor as s[N] and
        // count as 1
        curr = s[N];
        cnt = 1;
    }

    // Calculate the number
    // of even factors
    even = total - odd;

    // Print the difference
    System.out.print(Math.abs(even - odd));
}

// Driver Code
public static void main(String[] args)
{
    int N = 12;

    findDifference(N);
}
}

// This code is contributed by 29AjayKumar
```

## 蟒蛇 3

```python
# Python3 program for the above approach

# Function to find the smallest prime
# factor of all the numbers using
# Sieve Of Eratosthenes
def sieveOfEratosthenes(N, s):

    # Stores whether any number
    # is prime or not
    prime = [False]*(N + 1)

    # Initialize smallest factor as
    # 2 for all the even numbers
    for i in range(2, N + 1, 2):
        s[i] = 2

    # Iterate over the range [3, N]
    for i in range(3, N, 2):
        # If i is prime

        if (prime[i] == False):
            s[i] = i

            # Iterate all multiples of i
            for j in range(i, N, 2):
                if j * i > N:
                    break

                # i is the smallest
                # prime factor of i * j
                if (not prime[i * j]):
                    prime[i * j] = True
                    s[i * j] = i

# Function to find the absolute
# difference between the count
# of odd and even factors of N
def findDifference(N):

    # Stores the smallest
    # prime factor of i
    s = [0]*(N+1)

    # Fill values in s[] using
    # sieve of eratosthenes
    sieveOfEratosthenes(N, s)

    # Stores the total number of
    # factors and the total number
    # of odd and even factors
    total , odd , even =1, 1, 0

    # Store the current prime
    # factor of the number N
    curr = s[N]

    # Store the power of
    # current prime factor
    cnt = 1

    # Loop while N is greater than 1
    while (N > 1):
        N //= s[N]

        # If N also has smallest
        # prime factor as curr, then
        # increment cnt by 1
        if (curr == s[N]):
            cnt += 1
            continue

        # Update only total number
        # of factors if curr is 2
        if (curr == 2):
            total = total * (cnt + 1)

        # Update total number of
        # factors and total number
        # of odd factors
        else:
            total = total * (cnt + 1)
            odd = odd * (cnt + 1)

        # Update current prime
        # factor as s[N] and
        # count as 1
        curr = s[N]
        cnt = 1

    # Calculate the number
    # of even factors
    even = total - odd

    # Print the difference
    print(abs(even - odd))

# Driver Code
if __name__ == '__main__':
    N = 12
    findDifference(N)

    # This code is contributed by mohit kumar 29.
```

## C#

```csharp
// C# program for the above approach
using System;
class GFG
{

    // Function to find the smallest prime
    // factor of all the numbers using
    // Sieve Of Eratosthenes
    static void sieveOfEratosthenes(int N, int[] s)
    {
        // Stores whether any number
        // is prime or not
        bool[] prime = new bool[N + 1];

        // Initialize smallest factor as
        // 2 for all the even numbers
        for (int i = 2; i <= N; i += 2)
            s[i] = 2;

        // Iterate over the range [3, N]
        for (int i = 3; i <= N; i += 2) {

            // If i is prime
            if (prime[i] == false) {

                s[i] = i;

                // Iterate all multiples of i
                for (int j = i; j * i <= N; j += 2) {

                    // i is the smallest
                    // prime factor of i * j
                    if (!prime[i * j]) {
                        prime[i * j] = true;
                        s[i * j] = i;
                    }
                }
            }
        }
    }

    // Function to find the absolute
    // difference between the count
    // of odd and even factors of N
    static void findDifference(int N)
    {

        // Stores the smallest
        // prime factor of i
        int[] s = new int[N + 1];

        // Fill values in s[] using
        // sieve of eratosthenes
        sieveOfEratosthenes(N, s);

        // Stores the total number of
        // factors and the total number
        // of odd and even factors
        int total = 1, odd = 1, even = 0;

        // Store the current prime
        // factor of the number N
        int curr = s[N];

        // Store the power of
        // current prime factor
        int cnt = 1;

        // Loop while N is greater than 1
        while (N > 1) {
            N /= s[N];

            // If N also has smallest
            // prime factor as curr, then
            // increment cnt by 1
            if (curr == s[N]) {
                cnt++;
                continue;
            }

            // Update only total number
            // of factors if curr is 2
            if (curr == 2) {
                total = total * (cnt + 1);
            }

            // Update total number of
            // factors and total number
            // of odd factors
            else {
                total = total * (cnt + 1);
                odd = odd * (cnt + 1);
            }

            // Update current prime
            // factor as s[N] and
            // count as 1
            curr = s[N];
            cnt = 1;
        }

        // Calculate the number
        // of even factors
        even = total - odd;

        // Print the difference
        Console.Write(Math.Abs(even - odd));
    }

    // Driver Code
    public static void Main()
    {
        int N = 12;
        findDifference(N);
    }
}

// This code is contributed by ukasp.
```

## java 描述语言

```javascript
<script>
// Javascript implementation of the above approach

// Function to find the smallest prime
// factor of all the numbers using
// Sieve Of Eratosthenes
function sieveOfEratosthenes(N, s)
{

    // Stores whether any number
    // is prime or not
    let prime = Array.from({length: N+1}, (_, i) => 0);

    // Initialize smallest factor as
    // 2 for all the even numbers
    for(let i = 2; i <= N; i += 2)
        s[i] = 2;

    // Iterate over the range [3, N]
    for(let i = 3; i <= N; i += 2)
    {

        // If i is prime
        if (prime[i] == false)
        {
            s[i] = i;

            // Iterate all multiples of i
            for(let j = i; j * i <= N; j += 2)
            {

                // i is the smallest
                // prime factor of i * j
                if (!prime[i * j])
                {
                    prime[i * j] = true;
                    s[i * j] = i;
                }
            }
        }
    }
}

// Function to find the absolute
// difference between the count
// of odd and even factors of N
function findDifference(N)
{

    // Stores the smallest
    // prime factor of i
    let s = Array.from({length: N+1}, (_, i) => 0);

    // Fill values in s[] using
    // sieve of eratosthenes
    sieveOfEratosthenes(N, s);

    // Stores the total number of
    // factors and the total number
    // of odd and even factors
    let total = 1, odd = 1, even = 0;

    // Store the current prime
    // factor of the number N
    let curr = s[N];

    // Store the power of
    // current prime factor
    let cnt = 1;

    // Loop while N is greater than 1
    while (N > 1)
    {
        N /= s[N];

        // If N also has smallest
        // prime factor as curr, then
        // increment cnt by 1
        if (curr == s[N])
        {
            cnt++;
            continue;
        }

        // Update only total number
        // of factors if curr is 2
        if (curr == 2)
        {
            total = total * (cnt + 1);
        }

        // Update total number of
        // factors and total number
        // of odd factors
        else
        {
            total = total * (cnt + 1);
            odd = odd * (cnt + 1);
        }

        // Update current prime
        // factor as s[N] and
        // count as 1
        curr = s[N];
        cnt = 1;
    }

    // Calculate the number
    // of even factors
    even = total - odd;

    // Print the difference
   document.write(Math.abs(even - odd));
}

  // Driver Code

     let N = 12;

    findDifference(N);

</script>
```

`Output:`

`时间复杂度:` `O(N *(log log N))`
`辅助空间:` `O(N)`