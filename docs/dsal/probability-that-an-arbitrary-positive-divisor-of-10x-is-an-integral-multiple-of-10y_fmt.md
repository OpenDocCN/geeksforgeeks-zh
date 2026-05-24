# 10^x 的任意正除数是 10^Y 的整数倍的概率

> 原文: [https://www.geeksforgeeks.org/probability-that-an-arbitrary-positive-divisor-of-10x-is-an-integral-multiple-of-10y/](https://www.geeksforgeeks.org/probability-that-an-arbitrary-positive-divisor-of-10x-is-an-integral-multiple-of-10y/)

给定两个数字 `X` 和 `Y`，任务是求 `10^X` 的任意正除数是 `10^Y` 的整数倍的概率。
**注:** `Y` 应为 `<= X`。

**例:**

> **输入:** `X = 2`，`Y = 1`
> **输出:** `4/9`
> **说明:**
> `10^2` 的正因子为 1，2，4，5，10，20，25，50，100。一共 9 个。
> `10^1` 到 `10^2` 的倍数为 10，20，50，100。一共 4 个。
> `P(10^2` 的除数是 `10^1` 的倍数`) = 4/9`。
> **输入:** `X = 99`，`Y = 88`
> **输出:** `9/625`
> **解释:** `A = 10^99`，`B = 10^88` `P(10` 的除数 `^99` 是 `10` 的倍数 `^88` ) = 9/625`

**先决条件:** [一个数的除数总数](https://www.geeksforgeeks.org/total-number-divisors-given-number/)

**方法:**
为了解决问题，我们需要观察以下步骤:

*   `10^X` 的所有除数将为:
    > `(2^P * 5^Q)`，其中 `0 <= P, Q <= X`
*   求 `10^X` 的质因数数
    `10^X = 2^X * 5^X`
*   因此，`10^X` 的除数总数将为: `(X + 1) * (X + 1)`。
*   现在，考虑 `10^Y` 的所有倍数，它们可以是 `10^X` 的潜在约数。它们的形式还有:
    > `(2^A * 5^B)`，其中 `Y <= A, B <= X`
*   所以 `10^X` 的也是 `10^Y` 的倍数的潜在约数为 `(X–Y+1) * (X–Y+1)`。
*   因此，所需概率为 `((X–Y+1) * (X–Y+1)) / ((X+1) * (X+1))`。计算给定值 `X` 和 `Y` 的表达式的值，给出了所需的概率。

以下是上述方法的实现:

## C++

```cpp
// C++ program to find the probability
// of an arbitrary positive divisor of
// Xth power of 10 to be a multiple of
// Yth power of 10

#include <bits/stdc++.h>
using namespace std;
#define int long long int

// Function to calculate and print
// the required probability
void prob(int x, int y)
{
    // Count of potential divisors
    // of X-th power of 10 which are
    // also multiples of Y-th power
    // of 10
    int num = abs(x - y + 1)
              * abs(x - y + 1);

    // Count of divisors of X-th
    // power of 10
    int den = (x + 1) * (x + 1);

    // Calculate GCD
    int gcd = __gcd(num, den);

    // Print the reduced
    // fraction probability
    cout << num / gcd << "/"
         << den / gcd << endl;
}

// Driver Code
signed main()
{
    int X = 2, Y = 1;
    prob(X, Y);
    return 0;
}
```

## Java

```java
// Java program to find the probability
// of an arbitrary positive divisor of
// Xth power of 10 to be a multiple of
// Yth power of 10
import java.util.*;

class GFG{

// Function to calculate and print
// the required probability
static void prob(int x, int y)
{

    // Count of potential divisors
    // of X-th power of 10 which are
    // also multiples of Y-th power
    // of 10
    int num = Math.abs(x - y + 1) * 
              Math.abs(x - y + 1);

    // Count of divisors of X-th
    // power of 10
    int den = (x + 1) * (x + 1);

    // Calculate GCD
    int gcd = __gcd(num, den);

    // Print the reduced
    // fraction probability
    System.out.print(num / gcd + "/" + 
                     den / gcd + "\n");
}

static int __gcd(int a, int b) 
{ 
    return b == 0 ? a : __gcd(b, a % b);     
} 

// Driver code
public static void main(String[] args)
{
    int X = 2, Y = 1;

    prob(X, Y);
}
}

// This code is contributed by amal kumar choubey
```

## Python 3

```python
# Python3 program to find the probability
# of an arbitrary positive divisor of
# Xth power of 10 to be a multiple of
# Yth power of 10
from math import *

# Function to calculate and print
# the required probability
def prob(x, y):

    # Count of potential divisors
    # of X-th power of 10 which are
    # also multiples of Y-th power
    # of 10
    num = abs(x - y + 1) * abs(x - y + 1)

    # Count of divisors of X-th
    # power of 10
    den = (x + 1) * (x + 1)

    # Calculate GCD
    gcd1 = gcd(num, den)

    # Print the reduced
    # fraction probability
    print(num // gcd1, end = "")
    print("/", end = "")
    print(den // gcd1)

# Driver Code
if __name__ == '__main__':

    X = 2
    Y = 1

    prob(X, Y)

# This code is contributed by Surendra_Gangwar
```

## C#

```csharp
// C# program to find the probability 
// of an arbitrary positive divisor of 
// Xth power of 10 to be a multiple of 
// Yth power of 10 
using System;
class GFG{ 

// Function to calculate and print 
// the required probability 
static void prob(int x, int y) 
{ 

    // Count of potential divisors 
    // of X-th power of 10 which are 
    // also multiples of Y-th power 
    // of 10 
    int num = Math.Abs(x - y + 1) * 
              Math.Abs(x - y + 1); 

    // Count of divisors of X-th 
    // power of 10 
    int den = (x + 1) * (x + 1); 

    // Calculate GCD 
    int gcd = __gcd(num, den); 

    // Print the reduced 
    // fraction probability 
    Console.Write(num / gcd + "/" + 
                  den / gcd + "\n"); 
} 

static int __gcd(int a, int b) 
{ 
    return b == 0 ? a : __gcd(b, a % b);     
} 

// Driver code 
public static void Main(string[] args) 
{ 
    int X = 2, Y = 1; 

    prob(X, Y); 
} 
} 

// This code is contributed by AnkitRai01 
```

## JavaScript

```javascript
<script>

// JavaScript program to find the probability
// of an arbitrary positive divisor of
// Xth power of 10 to be a multiple of
// Yth power of 10

// Function to calculate and print
// the required probability
function prob(x, y)
{

    // Count of potential divisors
    // of X-th power of 10 which are
    // also multiples of Y-th power
    // of 10
    var num = Math.abs(x - y + 1) * 
              Math.abs(x - y + 1);

    // Count of divisors of X-th
    // power of 10
    var den = (x + 1) * (x + 1);

    // Calculate GCD
    var gcd = __gcd(num, den);

    // Print the reduced
    // fraction probability
    document.write(num / gcd + "/" + 
                   den / gcd + "\n");
}

function __gcd(a, b) 
{ 
    return b == 0 ? a : __gcd(b, a % b);     
} 

// Driver Code
var X = 2, Y = 1;

prob(X, Y);

// This code is contributed by Khushboogoyal499

</script>
```

**Output:**

```
4/9
```

`时间复杂度: O(log(N))`