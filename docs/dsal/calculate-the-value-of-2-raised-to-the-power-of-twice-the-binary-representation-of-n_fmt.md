# 计算 2 的 (2 乘以 N 的二进制表示) 次方的值

> 原文: [https://www.geeksforgeeks.org/calculate-the-value-of-2-raised-to-the-power-of-twice-the-binary-representation-of-n/](https://www.geeksforgeeks.org/calculate-the-value-of-2-raised-to-the-power-of-twice-the-binary-representation-of-n/)

给定一个正整数 `N`，任务是求 `(2^(2 * X))` 的值，其中 `X` 是 `N` 的[二进制表示](https://www.geeksforgeeks.org/binary-representation-of-a-given-number/)。由于答案可以很大，所以以 `10^9 + 7` 为模打印。

**示例:**

> **输入:** `N = 2`
> **输出:** `1048576`
> **说明:**
> 2 的二进制表示为 `(10)_2`。
> 因此，`(2^(2 * 10)) % (10^9 + 7) = (2^20) % (10^9 + 7) = 1048576`
>
> **输入:** `N = 150`
> **输出:** `654430484`

**天真法:** 解决这个问题最简单的方法就是[生成 N 的二进制表示](https://www.geeksforgeeks.org/binary-representation-of-a-given-number/)，记作 `X`，然后使用[模幂运算](https://www.geeksforgeeks.org/modular-exponentiation-power-in-modular-arithmetic/)计算 `(2^(2 * X)) % (10^9 + 7)` 的值。

下面是上述方法的实现：

## C++

```cpp
// C++ program to implement
// the above approach

#include <bits/stdc++.h>
using namespace std;
#define M 1000000007

// Function to find the value
// of power(X, Y) in O(log Y)
long long power(long long X,
                long long Y)
{
    // Stores power(X, Y)
    long long res = 1;

    // Update X
    X = X % M;

    // Base Case
    if (X == 0)
        return 0;

    // Calculate power(X, Y)
    while (Y > 0) {

        // If Y is an odd number
        if (Y & 1) {

            // Update res
            res = (res * X) % M;
        }

        // Update Y
        Y = Y >> 1;

        // Update X
        X = (X * X) % M;
    }

    return res;
}

// Function to calculate
// (2^(2 * x)) % (10^9 + 7)
int findValue(long long int n)
{

    // Stores binary
    // representation of n
    long long X = 0;

    // Stores power of 10
    long long pow_10 = 1;

    // Calculate the binary
    // representation of n
    while (n) {

        // If n is an odd number
        if (n & 1) {

            // Update X
            X += pow_10;
        }

        // Update pow_10
        pow_10 *= 10;

        // Update n
        n /= 2;
    }

    // Double the value of X
    X = (X * 2) % M;

    // Stores the value of
    // (2^(2 * x)) % (10^9 + 7)
    long long res = power(2, X);

    return res;
}

// Driver Code
int main()
{

    long long n = 2;
    cout << findValue(n);
    return 0;
}
```

## Java

```java
// Java program to implement
// the above approach
import java.util.*;
class GFG
{

  static int M  = 1000000007;

  // Function to find the value
  // of power(X, Y) in O(log Y)
  static int  power(int  X,
                    int  Y)
  {

    // Stores power(X, Y)
    int  res = 1;

    // Update X
    X = X % M;

    // Base Case
    if (X == 0)
      return 0;

    // Calculate power(X, Y)
    while (Y > 0)
    {

      // If Y is an odd number
      if ((Y & 1) != 0)
      {

        // Update res
        res = (res * X) % M;
      }

      // Update Y
      Y = Y >> 1;

      // Update X
      X = (X * X) % M;
    }
    return res;
  }

  // Function to calculate
  // (2^(2 * x)) % (10^9 + 7)
  static int findValue(int n)
  {

    // Stores binary
    // representation of n
    int  X = 0;

    // Stores power of 10
    int  pow_10 = 1;

    // Calculate the binary
    // representation of n
    while (n != 0)
    {

      // If n is an odd number
      if ((n & 1) != 0)
      {

        // Update X
        X += pow_10;
      }

      // Update pow_10
      pow_10 *= 10;

      // Update n
      n /= 2;
    }

    // Double the value of X
    X = (X * 2) % M;

    // Stores the value of
    // (2^(2 * x)) % (10^9 + 7)
    int  res = power(2, X);
    return res;
  }

  // Driver code
  public static void main(String[] args)
  {
    int  n = 2;
    System.out.println(findValue(n));
  }
}

// This code is contributed by susmitakundugoaldanga.
```

## Python 3

```python
# Python3 program to implement
# the above approach
M = 1000000007

# Function to find the value
# of power(X, Y) in O(log Y)
def power(X, Y):

    # Stores power(X, Y)
    res = 1

    # Update X
    X = X % M

    # Base Case
    if (X == 0):
        return 0

    # Calculate power(X, Y)
    while (Y > 0):

        # If Y is an odd number
        if (Y & 1):

            # Update res
            res = (res * X) % M

        # Update Y
        Y = Y >> 1

        # Update X
        X = (X * X) % M

    return res

# Function to calculate
# (2^(2 * x)) % (10^9 + 7)
def findValue(n):

    # Stores binary
    # representation of n
    X = 0

    # Stores power of 10
    pow_10 = 1

    # Calculate the binary
    # representation of n
    while(n):

        # If n is an odd number
        if (n & 1):

            # Update X
            X += pow_10

        # Update pow_10
        pow_10 *= 10

        # Update n
        n //= 2

    # Double the value of X
    X = (X * 2) % M

    # Stores the value of
    # (2^(2 * x)) % (10^9 + 7)
    res = power(2, X)

    return res

# Driver Code
if __name__ == "__main__":

    n = 2

    print(findValue(n))

# This code is contributed by AnkThon
```

## C#

```csharp
// C# program to implement
// the above approach
using System;
class GFG
{

  static int M  = 1000000007;

  // Function to find the value
  // of power(X, Y) in O(log Y)
  static int  power(int  X,
                    int  Y)
  {

    // Stores power(X, Y)
    int  res = 1;

    // Update X
    X = X % M;

    // Base Case
    if (X == 0)
      return 0;

    // Calculate power(X, Y)
    while (Y > 0)
    {

      // If Y is an odd number
      if ((Y & 1) != 0)
      {

        // Update res
        res = (res * X) % M;
      }

      // Update Y
      Y = Y >> 1;

      // Update X
      X = (X * X) % M;
    }
    return res;
  }

  // Function to calculate
  // (2^(2 * x)) % (10^9 + 7)
  static int findValue(int n)
  {

    // Stores binary
    // representation of n
    int  X = 0;

    // Stores power of 10
    int  pow_10 = 1;

    // Calculate the binary
    // representation of n
    while (n != 0)
    {

      // If n is an odd number
      if ((n & 1) != 0)
      {

        // Update X
        X += pow_10;
      }

      // Update pow_10
      pow_10 *= 10;

      // Update n
      n /= 2;
    }

    // Double the value of X
    X = (X * 2) % M;

    // Stores the value of
    // (2^(2 * x)) % (10^9 + 7)
    int  res = power(2, X);
    return res;
  }

  // Driver code
  public static void Main(String[] args)
  {
    int  n = 2;
    Console.WriteLine(findValue(n));
  }
}

// This code is contributed by shikhasingrajput
```

## JavaScript 描述

```javascript
<script>

// javascript program to implement
// the above approach
M = 1000000007;

// Function to find the value
// of power(X, Y) in O(log Y)
function power(X, Y) {

    // Stores power(X, Y)
    var res = 1;

    // Update X
    X = X % M;

    // Base Case
    if (X == 0)
        return 0;

    // Calculate power(X, Y)
    while (Y > 0) {

        // If Y is an odd number
        if ((Y & 1) != 0) {

            // Update res
            res = (res * X) % M;
        }

        // Update Y
        Y = Y >> 1;

        // Update X
        X = (X * X) % M;
    }
    return res;
}

// Function to calculate
// (2^(2 * x)) % (10^9 + 7)
function findValue(n) {

    // Stores binary representation of n
    var X = 0;

    // Stores power of 10
    var pow_10 = 1;

    // Calculate the binary representation of n
    while (n != 0) {

        // If n is an odd number
        if ((n & 1) != 0) {

            // Update X
            X += pow_10;
        }

        // Update pow_10
        pow_10 *= 10;

        // Update n
        n /= 2;
    }

    // Double the value of X
    X = (X * 2) % M;

    // Stores the value of (2^(2 * x)) % (10^9 + 7)
    var res = power(2, X);
    return res;
}

// Driver code
var n = 2;
document.write(findValue(n));

// This code is contributed by 29AjayKumar

</script>
```

**输出：**

**时间复杂度：** `O(log2(X))`，其中 `X` 为 `N` 的二进制表示
**辅助空间：** `O(1)`

## 优化方法

**有效方法：** 上述方法可以使用[动态规划](https://www.geeksforgeeks.org/dynamic-programming/)基于以下观察进行优化：

> 如果 `N == 1`，则所需输出为 `(2^1)^2 = (2^1)^2`
> 如果 `N == 2`，则所需输出为 `(2^10)^2 = (2^10)^2`
> 如果 `N == 3`，则所需输出为 `(2^11 * 2^1)^2`
> 如果 `N == 4`，则要求的输出为 `(2^100)^2 = (2^100)^2`
> 如果 `N == 5`，则要求的输出为 `(2^101)^2 = (2^100 ...`
> 下面是动态编程状态之间的关系：
> [如果 `N` 是 2 的幂](https://www.geeksforgeeks.org/program-to-find-whether-a-no-is-power-of-two/)，那么 `dp[N] = power(dp[N / 2], 10)`
> 否则，`DP[N] = DP[(N & (-N))] * DP[N – (N & (-N))]`
> `DP[N]^2`：存储正整数所需的输出

按照以下步骤解决问题：

*   初始化一个数组，比如说 `dp[]`，这样 `DP[I]^2` 存储 `(2^(2 * X)) % (10^9 + 7)` 的值，其中 `X` 是 `i` 的二进制表示。
*   使用变量 `i` 迭代范围 `[3, N]`，并使用制表方法找到 `dp[i]` 的所有可能值。
*   最后，打印 `DP[N]^2` 的值

## C++

```cpp
// C++ program to implement
// the above approach

#include <bits/stdc++.h>
using namespace std;
#define M 1000000007

// Function to find the value
// of power(X, Y) in O(log Y)
long long power(long long X,
                long long Y)
{
    // Stores power(X, Y)
    long long res = 1;

    // Update X
    X = X % M;

    // Base Case
    if (X == 0)
        return 0;

    // Calculate power(X, Y)
    while (Y > 0) {

        // If Y is an odd number
        if (Y & 1) {

            // Update res
            res = (res * X) % M;
        }

        // Update Y
        Y = Y >> 1;

        // Update X
        X = (X * X) % M;
    }

    return res;
}

// Function to calculate
// (2^(2 * x)) % (10^9 + 7)
long long findValue(long long N)
{

    // dp[N] * dp[N]: Stores value
    // of (2^(2 * x)) % (10^9 + 7)
    long long dp[N + 1];

    // Base Case
    dp[1] = 2;
    dp[2] = 1024;

    // Iterate over the range [3, N]
    for (int i = 3; i <= N; i++) {

        // Stores rightmost bit of i
        int y = (i & (-i));

        // Stores the value of (i - y)
        int x = i - y;

        // If x is power of 2
        if (x == 0) {

            // Update dp[i]
            dp[i]
                = power(dp[i / 2], 10);
        }
        else {

            // Update dp[i]
            dp[i]
                = (dp[x] * dp[y]) % M;
        }
    }

    return (dp[N] * dp[N]) % M;
}

// Driver Code
int main()
{

    long long n = 150;
    cout << findValue(n);
    return 0;
}
```

## Java

```java
// Java program to implement
// the above approach
class GFG
{
  static final long M = 1000000007;

  // Function to find the value
  // of power(X, Y) in O(log Y)
  static long power(long X,
                    long Y)
  {

    // Stores power(X, Y)
    long res = 1;

    // Update X
    X = X % M;

    // Base Case
    if (X == 0)
      return 0;

    // Calculate power(X, Y)
    while (Y > 0)
    {

      // If Y is an odd number
      if (Y % 2 == 1)
      {

        // Update res
        res = (res * X) % M;
      }

      // Update Y
      Y = Y >> 1;

      // Update X
      X = (X * X) % M;
    }

    return res;
  }

  // Function to calculate
  // (2^(2 * x)) % (10^9 + 7)
  static long findValue(int N)
  {

    // dp[N] * dp[N]: Stores value
    // of (2^(2 * x)) % (10^9 + 7)
    long []dp = new long[N + 1];

    // Base Case
    dp[1] = 2;
    dp[2] = 1024;

    // Iterate over the range [3, N]
    for (int i = 3; i <= N; i++)
    {

      // Stores rightmost bit of i
      int y = (i & (-i));

      // Stores the value of (i - y)
      int x = i - y;

      // If x is power of 2
      if (x == 0)
      {

        // Update dp[i]
        dp[i]
          = power(dp[i / 2], 10);
      }
      else
      {

        // Update dp[i]
        dp[i]
          = (dp[x] * dp[y]) % M;
      }
    }
    return (dp[N] * dp[N]) % M;
  }

  // Driver Code
  public static void main(String[] args)
  {
    int n = 150;
    System.out.print(findValue(n));
  }
}

// This code is contributed by shikhasingrajput
```

## Python 3

```python
# Python3 program to implement
# the above approach
M = 1000000007;

# Function to find the value
# of power(X, Y) in O(log Y)
def power(X, Y):

    # Stores power(X, Y)
    res = 1;

    # Update X
    X = X % M;

    # Base Case
    if (X == 0):
        return 0;

    # Calculate power(X, Y)
    while (Y > 0):

        # If Y is an odd number
        if (Y % 2 == 1):

            # Update res
            res = (res * X) % M;

        # Update Y
        Y = Y >> 1;

        # Update X
        X = (X * X) % M;
    return res;

# Function to calculate
# (2^(2 * x)) % (10^9 + 7)
def findValue(N):

    # dp[N] * dp[N]: Stores value
    # of (2^(2 * x)) % (10^9 + 7)
    dp = [0]*(N + 1);

    # Base Case
    dp[1] = 2;
    dp[2] = 1024;

    # Iterate over the range [3, N]
    for i in range(3, N + 1):

        # Stores rightmost bit of i
        y = (i & (-i));

        # Stores the value of (i - y)
        x = i - y;

        # If x is power of 2
        if (x == 0):

            # Update dp[i]
            dp[i] = power(dp[i // 2], 10);
        else:

            # Update dp[i]
            dp[i] = (dp[x] * dp[y]) % M;

    return (dp[N] * dp[N]) % M;

# Driver Code
if __name__ == '__main__':
    n = 150;
    print(findValue(n));

# This code is contributed by 29AjayKumar
```

# C#

```csharp
// C# program to implement
// the above approach
using System;
class GFG
{
  static readonly long M = 1000000007;

  // Function to find the value
  // of power(X, Y) in O(log Y)
  static long power(long X,
                    long Y)
  {

    // Stores power(X, Y)
    long res = 1;

    // Update X
    X = X % M;

    // Base Case
    if (X == 0)
      return 0;

    // Calculate power(X, Y)
    while (Y > 0)
    {

      // If Y is an odd number
      if (Y % 2 == 1)
      {

        // Update res
        res = (res * X) % M;
      }

      // Update Y
      Y = Y >> 1;

      // Update X
      X = (X * X) % M;
    }

    return res;
  }

  // Function to calculate
  // (2^(2 * x)) % (10^9 + 7)
  static long findValue(int N)
  {

    // dp[N] * dp[N]: Stores value
    // of (2^(2 * x)) % (10^9 + 7)
    long []dp = new long[N + 1];

    // Base Case
    dp[1] = 2;
    dp[2] = 1024;

    // Iterate over the range [3, N]
    for (int i = 3; i <= N; i++)
    {

      // Stores rightmost
      // bit of i
      int y = (i & (-i));

      // Stores the value
      // of (i - y)
      int x = i - y;

      // If x is power
      // of 2
      if (x == 0)
      {

        // Update dp[i]
        dp[i]
          = power(dp[i / 2], 10);
      }
      else
      {

        // Update dp[i]
        dp[i]
          = (dp[x] * dp[y]) % M;
      }
    }
    return (dp[N] * dp[N]) % M;
  }

  // Driver Code
  public static void Main(String[] args)
  {
    int n = 150;
    Console.Write(findValue(n));
  }
}

// This code contributed by shikhasingrajput
```

`Output:`

`时间复杂度:` `O(N *log(N))`
`辅助空间:` `O(N)`