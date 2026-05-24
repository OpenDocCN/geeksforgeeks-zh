# 乘完全数

> 原文: [https://www.geeksforgeeks.org/multiply-perfect-number/](https://www.geeksforgeeks.org/multiply-perfect-number/)

一个数 `N` 如果 `N` 整除 `σ(N)`，其中 `σ(N)` 是 `N` 的所有除数之和，则称之为乘完全数。
前几个乘完全数是：

> 1, 6, 28, 120, 496, 672, ……

## 检查 N 是否是一个乘完全数

给定一个数 `N`，任务是找出这个数是否是乘完全数。

**例：**

> **输入：** `N = 120`
> **输出：** YES
> **解释：**
> 120 的除数之和为 1+2+3+4+5+6+8+10+12+15+20+24+30+40+60+120 = 360，120 整除 360。
> 因此，120 是一个乘完全数。
> **输入：** `N = 32`
> **输出：** NO

**方法：** 对于一个数 `N` 为乘完全数，以下条件成立：`σ(N) % N = 0`，其中 `σ(N)` 是 `N` 的所有除数之和。因此，我们将找到 `N` 的所有除数的和，并检查它是否能被 `N` 整除。如果可整除则打印 `"YES"`，否则打印 `"NO"`。

以下是上述方法的实现：

### C++

```cpp
// C++ implementation of the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find the sum of divisors
int getSum(int n)
{
    int sum = 0;

    // Note that this loop runs till square root of N
    for (int i = 1; i <= sqrt(n); i++) {
        if (n % i == 0) {

            // If divisors are equal, take only one of them
            if (n / i == i)
                sum = sum + i;

            // Otherwise take both
            else {
                sum = sum + i;
                sum = sum + (n / i);
            }
        }
    }

    return sum;
}

// Function to check Multiply-perfect number
bool MultiplyPerfectNumber(int n)
{
    if (getSum(n) % n == 0)
        return true;
    else
        return false;
}

// Driver code
int main()
{
    int n = 28;
    if (MultiplyPerfectNumber(n)) {
        cout << "Yes";
    }
    else {
        cout << "No";
    }
    return 0;
}
```

### Java

```java
// Java implementation of the above approach
class GFG{

// Function to find the sum of divisors
static int getSum(int n)
{
    int sum = 0;

    // Note that this loop runs till square root of N
    for(int i = 1; i <= Math.sqrt(n); i++)
    {
       if (n % i == 0)
       {

           // If divisors are equal, take only one of them
           if (n / i == i)
               sum = sum + i;

           // Otherwise take both
           else
           {
               sum = sum + i;
               sum = sum + (n / i);
           }
       }
    }
    return sum;
}

// Function to check Multiply-perfect number
static boolean MultiplyPerfectNumber(int n)
{
    if (getSum(n) % n == 0)
        return true;
    else
        return false;
}

// Driver code
public static void main(String[] args)
{
    int n = 28;

    if (MultiplyPerfectNumber(n))
    {
        System.out.print("Yes");
    }
    else
    {
        System.out.print("No");
    }
}
}

// This code is contributed by Ritik Bansal
```

### Python 3

```python
# Python3 implementation of the above approach
import math

# Function to find the sum of divisors
def getSum(n):
    sum1 = 0;

    # Note that this loop runs till square root of N
    for i in range(1, int(math.sqrt(n))):
        if (n % i == 0):

            # If divisors are equal, take only one of them
            if (n // i == i):
                sum1 = sum1 + i;

            # Otherwise take both
            else:
                sum1 = sum1 + i;
                sum1 = sum1 + (n // i);

    return sum1;

# Function to check Multiply-perfect number
def MultiplyPerfectNumber(n):
    if (getSum(n) % n == 0):
        return True;
    else:
        return False;

# Driver code
n = 28;
if (MultiplyPerfectNumber(n)):
    print("Yes");
else:
    print("No");

# This code is contributed by Code_Mech
```

### C#

```csharp
// C# implementation of the above approach
using System;
class GFG{

// Function to find the sum of divisors
static int getSum(int n)
{
    int sum = 0;

    // Note that this loop runs till square root of N
    for(int i = 1; i <= Math.Sqrt(n); i++)
    {
       if (n % i == 0)
       {

           // If divisors are equal, take only one of them
           if (n / i == i)
               sum = sum + i;

           // Otherwise take both
           else
           {
               sum = sum + i;
               sum = sum + (n / i);
           }
       }
    }
    return sum;
}

// Function to check Multiply-perfect number
static bool MultiplyPerfectNumber(int n)
{
    if (getSum(n) % n == 0)
        return true;
    else
        return false;
}

// Driver code
public static void Main()
{
    int n = 28;

    if (MultiplyPerfectNumber(n))
    {
        Console.Write("Yes");
    }
    else
    {
        Console.Write("No");
    }
}
}

// This code is contributed by Code_Mech
```

### JavaScript

```javascript
<script>
// Javascript implementation of the above approach

// Function to find the sum of divisors
function getSum(n)
{
    let sum = 0;

    // Note that this loop runs till square root of N
    for (i = 1; i <= Math.sqrt(n); i++)
    {
        if (n % i == 0)
        {

            // If divisors are equal, take only one of them
            if (n / i == i)
                sum = sum + i;

            // Otherwise take both
            else {
                sum = sum + i;
                sum = sum + (n / i);
            }
        }
    }
    return sum;
}

// Function to check Multiply-perfect number
function MultiplyPerfectNumber(n) {
    if (getSum(n) % n == 0)
        return true;
    else
        return false;
}

// Driver code
let n = 28;
if (MultiplyPerfectNumber(n)) {
    document.write("Yes");
} else {
    document.write("No");
}

// This code is contributed by Rajput-Ji
</script>
```

**输出：**

```
Yes
```

**时间复杂度：** `O(N^{1/2})`

**辅助空间：** `O(1)`

**参考文献：** [https://en.wikipedia.org/wiki/Multiply_perfect_number](https://en.wikipedia.org/wiki/Multiply_perfect_number)