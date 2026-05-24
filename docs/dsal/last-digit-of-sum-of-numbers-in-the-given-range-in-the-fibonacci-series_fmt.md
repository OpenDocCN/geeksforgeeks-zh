# 斐波那契数列中给定范围内数字总和的最后一位数字

> 原文：[https://www.geeksforgeeks.org/last-digit-of-sum-of-numbers-in-the-given-range-in-the-fibonacci-series/](https://www.geeksforgeeks.org/last-digit-of-sum-of-numbers-in-the-given-range-in-the-fibonacci-series/)

## 问题描述

给定两个非负整数 `M` 和 `N`，表示范围 `[M, N]`（其中 `M ≤ N`），任务是求 `F_M + F_{M+1} + …… + F_N` 的和的最后一位数字，其中 `F_K` 是[斐波那契数列](https://www.geeksforgeeks.org/program-for-nth-fibonacci-number/)中的第 `K` 个[斐波那契数](https://www.geeksforgeeks.org/program-for-nth-fibonacci-number/)。

> 0、1、1、2、3、5、8、13、21、34、55、89、144……

## 示例

> **输入:** `M = 3`，`N = 9`
> **输出:** 6
> **解释:**
> 我们需要找到 `F_3 + F_4 + F_5 + F_6 + F_7 + F_8 + F_9`
> =>
> 很明显，总和的最后一位数字是 6。

> **输入:** `M = 3`，`N = 7`
> **输出:** 1
> **解释:**
> 我们需要找到 `F_3 + F_4 + F_5 + F_6 + F_7`
> => 2 + 3 + 5 + 8 + 13 = 31
> 很明显，总和的最后一位是 1。

## 方法

**天真法:** 这个问题的天真法是一个接一个地求出所有第 `K` 个斐波那契数的和，其中 `K` 位于范围 `[M, N]` 内，最后返回和的最后一位数字。这种方法的时间复杂度是 `O(N)`，并且对于 `N` 的高阶值是失败的。

**有效方法:** 解决这个问题的有效方法是使用[皮萨诺周期](https://www.geeksforgeeks.org/fibonacci-number-modulo-m-and-pisano-period/)的概念。

*   其思想是分别计算第 `(M–1)` 个和第 `N` 个斐波那契数之前所有项的和，并减去这两个计算值的最后一位。
*   这是因为范围 `[M, N]` 内所有第 `K` 个斐波那契数之和的最后一位，等于范围 `[0, N]` 内所有第 `K` 个斐波那契数之和的最后一位与范围 `[0, M–1]` 内所有第 `K` 个斐波那契数之和的最后一位的差。
*   这些值可以分别用皮萨诺周期的概念在很短的时间内计算出来。
*   让我们了解一下皮萨诺周期是如何运作的。下表说明了前 10 个斐波那契数以及对这些数进行模 2 时获得的值。

| i | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| F_i | 0 | 1 | 1 | 2 | 3 | 5 | 8 | 13 | 21 | 34 | 55 |
| F_i mod 2 | 0 | 1 | 1 | 0 | 1 | 1 | 0 | 1 | 1 | 0 | 1 |

*   显然，`(F_i mod 2)` 的皮萨诺周期是 3，因为 `011` 自身重复，长度为 3。
*   现在，让我们观察以下恒等式：

> 7 = 2 * 3 + 1
> 被除数 = (商 × 除数) + 余数
> => `F_7 mod 2 = F_1 mod 2 = 1`。

*   因此，我们不计算范围 `[0, N]` 中所有数字之和的最后一位，而是简单地计算该和，直到给定 `F_i mod 10` 的皮萨诺周期为 60 的余数。

## 实现

以下是上述方法的实现：

### C++

```cpp
// C++ program to calculate
// last digit of the sum of the
// fibonacci numbers from M to N
#include<bits/stdc++.h>
using namespace std;

// Calculate the sum of the first
// N Fibonacci numbers using Pisano
// period
long long fib(long long n)
{

    // The first two Fibonacci numbers
    long long f0 = 0;
    long long f1 = 1;

    // Base case
    if (n == 0)
        return 0;
    if (n == 1)
        return 1;
    else
    {
        // Pisano period for % 10 is 60
        long long rem = n % 60;

        // Checking the remainder
        if(rem == 0)
           return 0;

        // The loop will range from 2 to
        // two terms after the remainder
        for(long long i = 2; i < rem + 3; i++)
        {
           long long f = (f0 + f1) % 60;
           f0 = f1;
           f1 = f;
        }

        long long s = f1 - 1;
        return s;
    }
}

// Driver Code
int main()
{
    long long m = 10087887;
    long long n = 2983097899;

    long long final = abs(fib(n) - fib(m - 1));
    cout << final % 10 << endl;
}

// This code is contributed by Bhupendra_Singh
```

### Java

```java
// Java program to calculate
// last digit of the sum of the
// fibonacci numbers from M to N
import java.util.*;

class GFG{

// Calculate the sum of the first
// N Fibonacci numbers using Pisano
// period
static int fib(long n)
{

    // The first two Fibonacci numbers
    int f0 = 0;
    int f1 = 1;

    // Base case
    if (n == 0)
        return 0;
    if (n == 1)
        return 1;
    else
    {

        // Pisano period for % 10 is 60
        int rem = (int) (n % 60);

        // Checking the remainder
        if(rem == 0)
        return 0;

        // The loop will range from 2 to
        // two terms after the remainder
        for(int i = 2; i < rem + 3; i++)
        {
           int f = (f0 + f1) % 60;
           f0 = f1;
           f1 = f;
        }

        int s = f1 - 1;
        return s;
    }
}

// Driver Code
public static void main(String args[])
{
    int m = 10087887;
    long n = 2983097899L;
    int Final = (int)Math.abs(fib(n) -
                              fib(m - 1));

    System.out.println(Final % 10);
}
}

// This code is contributed by AbhiThakur
```

### Python 3

```python
# Python3 program to calculate
# Last Digit of the sum of the
# Fibonacci numbers from M to N

# Calculate the sum of the first
# N Fibonacci numbers using Pisano
# period
def fib(n):

    # The first two Fibonacci numbers
    f0 = 0
    f1 = 1

    # Base case
    if (n == 0):
        return 0
    if (n == 1):
        return 1
    else:

        # Pisano Period for % 10 is 60
        rem = n % 60

        # Checking the remainder
        if(rem == 0):
            return 0

        # The loop will range from 2 to
        # two terms after the remainder
        for i in range(2, rem + 3):
            f =(f0 + f1)% 60
            f0 = f1
            f1 = f

        s = f1-1
        return(s)

# Driver code
if __name__ == '__main__':

    m = 10087887
    n = 2983097899

    final = fib(n)-fib(m-1)

    print(final % 10)
```

### C#

```csharp
// C# program to calculate
// last digit of the sum of the
// fibonacci numbers from M to N
using System;

class GFG{

// Calculate the sum of the first
// N fibonacci numbers using Pisano
// period
static int fib(long n)
{

    // The first two fibonacci numbers
    int f0 = 0;
    int f1 = 1;

    // Base case
    if (n == 0)
        return 0;
    if (n == 1)
        return 1;
    else
    {

        // Pisano period for % 10 is 60
        int rem = (int)(n % 60);

        // Checking the remainder
        if(rem == 0)
           return 0;

        // The loop will range from 2 to
        // two terms after the remainder
        for(int i = 2; i < rem + 3; i++)
        {
           int f = (f0 + f1) % 60;
           f0 = f1;
           f1 = f;
        }

        int s = f1 - 1;
        return s;
    }
}

// Driver Code
public static void Main()
{
    int m = 10087887;
    long n = 2983097899L;
    int Final = (int)Math.Abs(fib(n) -
                              fib(m - 1));

    Console.WriteLine(Final % 10);
}
}

// This code is contributed by Code_Mech
```

### JavaScript

```javascript
<script>
// javascript program to calculate
// last digit of the sum of the
// fibonacci numbers from M to N

    // Calculate the sum of the first
    // N Fibonacci numbers using Pisano
    // period
    function fib(n) {

        // The first two Fibonacci numbers
        var f0 = 0;
        var f1 = 1;

        // Base case
        if (n == 0)
            return 0;
        if (n == 1)
            return 1;
        else {

            // Pisano period for % 10 is 60
            var rem = parseInt( (n % 60));

            // Checking the remainder
            if (rem == 0)
                return 0;

            // The loop will range from 2 to
            // two terms after the remainder
            for (i = 2; i < rem + 3; i++) {
                var f = (f0 + f1) % 60;
                f0 = f1;
                f1 = f;
            }

            var s = f1 - 1;
            return s;
        }
    }

    // Driver Code
    var m = 10087887;
    var n = 2983097899;
    var Final = parseInt( Math.abs(fib(n) - fib(m - 1)));

    document.write(Final % 10);

// This code is contributed by Rajput-Ji
</script>
```

## 复杂度分析

**时间复杂度:** `O(1)`，因为这个代码对于任何输入的数字都要运行差不多 60 次。

**辅助空间:** `O(1)`