# 从 N 的 K 次幂中找出第一个和最后一个 M 位

> 原文: [https://www.geeksforgeeks.org/find-the-first-and-last-m-digits-from-k-th-power-of-n/](https://www.geeksforgeeks.org/find-the-first-and-last-m-digits-from-k-th-power-of-n/)

给定两个整数 `N` 和 `K`，任务是找到数字 `N^K` 的第一个 `M` 和最后一个 `M` 位数。

**示例:**

> **输入:** `N = 2345`，`K = 3`，`M = 3`
> **输出:** `128 625`
> **说明:**
> `2345^3 = 12895213625`
> 因此，前 `M(= 3)` 位为 `128`，后三位为 `625`。

> **输入:** `N = 12`，`K = 12`，`M = 4`
> **输出:** `8916 8256`
> **解释:**
> `12^12 = 8916100448256`

### 天真法
解决问题最简单的方法就是计算 `N^K` 的值，迭代到第一个 `M` 位，通过 `N^K mod 10^M` 找到最后的 M 位。
**时间复杂度:** `O(K)`
**辅助空间:** `O(1)`

### 高效途径
通过以下观察可以优化上述途径:

> 让我们考虑一个数字 `x`，可以写成 `10^y`，其中 `y` 是十进制数。
> 令 `x = N^K`
> `N^K = 10^y`
> 取上述表达式两边的 `log10`，我们得到:
> `K * log10(N) = log10(10^y) = y`
> 因此，
> `N^K = 10^(abc...xyz...)`
> => `N^K = 10^(abc... + 0.xyz...)`
> => `N^K = 10^(abc...) * 10^(0.xyz...)`
> 在上式中，`10^(abc...)` 只向前移动小数点。
> 通过计算 `10^(0.xyz...)`，向前移动小数点可以算出第一个 `M` 位。

按照以下步骤解决问题:

*   通过计算 `(N^K) mod (10^M)` 找到 `N^K` 的最后 `M` 位。
*   计算 `K * log10(N)`。
*   计算 `10^(K * log10(N))`。
*   通过计算 `10^(K * log10(N)) * 10^(M–1)` 找到第一个 `M` 数字。
*   打印获得的第一个和最后一个 `M` 数字。

以下是上述方法的实现:

## C++

```cpp
// C++ Program to implement
// the above approach
#include <bits/stdc++.h>
#define ll long long int
using namespace std;

// Function to find a^b modulo M
ll modPower(ll a, ll b, ll M)
{
    ll res = 1;
    while (b) {
        if (b & 1)
            res = res * a % M;
        a = a * a % M;
        b >>= 1;
    }
    return res;
}

// Function to find the first and last
// M digits from N^K
void findFirstAndLastM(ll N, ll K, ll M)
{
    // Calculate Last M digits
    ll lastM
        = modPower(N, K, (1LL) * pow(10, M));

    // Calculate First M digits
    ll firstM;

    double y = (double)K * log10(N * 1.0);

    // Extract the number after decimal
    y = y - (ll)y;

    // Find 10 ^ y
    double temp = pow(10.0, y);

    // Move the Decimal Point M - 1 digits forward
    firstM = temp * (1LL) * pow(10, M - 1);

    // Print the result
    cout << firstM << " " << lastM << endl;
}

// Driver Code
int main()
{
    ll N = 12, K = 12, M = 4;

    findFirstAndLastM(N, K, M);
    return 0;
}
```

## Java

```java
// Java program to implement
// the above approach
class GFG{

// Function to find a^b modulo M
static long modPower(long a, long b, long M)
{
    long res = 1;
    while (b > 0)
    {
        if (b % 2 == 1)
            res = res * a % M;

        a = a * a % M;
        b >>= 1;
    }
    return res;
}

// Function to find the first and last
// M digits from N^K
static void findFirstAndLastM(long N, long K,
                              long M)
{

    // Calculate Last M digits
    long lastM = modPower(N, K, (1L) *
                 (long)Math.pow(10, M));

    // Calculate First M digits
    long firstM;

    double y = (double)K * Math.log10(N * 1.0);

    // Extract the number after decimal
    y = y - (long)y;

    // Find 10 ^ y
    double temp = Math.pow(10.0, y);

    // Move the Decimal Point M - 1 digits forward
    firstM = (long)(temp * (1L) *
             Math.pow(10, (M - 1)));

    // Print the result
    System.out.print(firstM + " " +
                      lastM + "\n");
}

// Driver Code
public static void main(String[] args)
{
    long N = 12, K = 12, M = 4;

    findFirstAndLastM(N, K, M);
}
}

// This code is contributed by Rajput-Ji
```

## Python 3

```python
# Python3 program to implement
# the above approach
from math import *

# Function to find a^b modulo M
def modPower(a, b, M):

    res = 1
    while (b):
        if (b & 1):
            res = res * a % M

        a = a * a % M
        b >>= 1

    return res

# Function to find the first and
# last M digits from N^K
def findFirstAndLastM(N, K, M):

    # Calculate Last M digits
    lastM = modPower(N, K, int(pow(10, M)))

    # Calculate First M digits
    firstM = 0

    y = K * log10(N * 1.0)

    # Extract the number after decimal
    y = y - int(y)

    # Find 10 ^ y
    temp = pow(10.0, y)

    # Move the Decimal Point M - 1
    # digits forward
    firstM = int(temp * pow(10, M - 1))

    # Print the result
    print(firstM, lastM)

# Driver Code
N = 12
K = 12
M = 4

findFirstAndLastM(N, K, M)

# This code is contributed by himanshu77
```

## C#

```csharp
// C# program to implement
// the above approach
using System;
using System.Collections.Generic;

class GFG{

// Function to find a^b modulo M
static long modPower(long a, long b, long M)
{
    long res = 1;
    while (b > 0)
    {
        if (b % 2 == 1)
            res = res * a % M;

        a = a * a % M;
        b >>= 1;
    }
    return res;
}

// Function to find the first and last
// M digits from N^K
static void findFirstAndLastM(long N, long K,
                              long M)
{

    // Calculate Last M digits
    long lastM = modPower(N, K, (1L) *
                 (long)Math.Pow(10, M));

    // Calculate First M digits
    long firstM;

    double y = (double)K * Math.Log10(N * 1.0);

    // Extract the number after decimal
    y = y - (long)y;

    // Find 10 ^ y
    double temp = Math.Pow(10.0, y);

    // Move the Decimal Point M - 1 digits forward
    firstM = (long)(temp * (1L) *
             Math.Pow(10, (M - 1)));

    // Print the result
    Console.Write(firstM + " " +
                   lastM + "\n");
}

// Driver Code
public static void Main(String[] args)
{
    long N = 12, K = 12, M = 4;

    findFirstAndLastM(N, K, M);
}
}

// This code is contributed by gauravrajput1
```

## JavaScript

```javascript
<script>

// JavaScript Program to implement
// the above approach

// Function to find a^b modulo M
function modPower(a, b, M)
{
    var res = 1;
    while (b) {
        if (b & 1)
            res = res * a % M;
        a = a * a % M;
        b >>= 1;
    }
    return res;
}

// Function to find the first and last
// M digits from N^K
function findFirstAndLastM(N, K, M)
{
    // Calculate Last M digits
    var lastM
        = modPower(N, K, Math.pow(10, M));

    // Calculate First M digits
    var firstM;

    var y = K * Math.log10(N * 1.0);

    // Extract the number after decimal
    y = y - parseInt(y);

    // Find 10 ^ y
    var temp = Math.pow(10.0, y);

    // Move the Decimal Point M - 1 digits forward
    firstM = temp  * Math.pow(10, M - 1);

    // Print the result
    document.write( parseInt(firstM) + " "
    + parseInt(lastM) );
}

// Driver Code
var N = 12, K = 12, M = 4;
findFirstAndLastM(N, K, M);

</script>
```

**Output:**

```
8916 8256
```

**时间复杂度:** `O(log K)`
**辅助空间:** `O(1)`