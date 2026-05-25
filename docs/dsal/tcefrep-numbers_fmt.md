# Tceforp 编号

> 原文: [https://www.geeksforgeeks.org/tcefrep-numbers/](https://www.geeksforgeeks.org/tcefrep-numbers/)

一个数 `N` 使得 `N` 的正因子之和等于 `N` 的反序数，称为 Tceforp 数。
例如：6, 498906, 20671542, 41673714….

## 检查 N 是否是一个 Tcefrep 号码

给定一个数 `N`，任务是检查 `N` 是否为 Tcefrep 编号。如果 `N` 是 Tcefrep 号，则打印“是”，否则打印“否”。

**示例:**

> **输入:** `N = 498906`
> **输出:** 是
> **解释:**
> 498906 的真因子是 1、2、3、6、9、18、27、54、9239、18478、27717、55434、83151、166302、249453，
> 它们的和是 600006，而 498906 的反序数是 609894？（原文此处和似乎有误，但逻辑描述保留）

**方法:**

1.  找到 `N` 的真因子之和。
2.  计算 `N` 的反序数。
3.  然后检查 `N` 的真因子之和是否等于 `N` 的反序数，如果等于则打印“是”，否则打印“否”。

以下是上述方法的实现：

## C++

```cpp
// C++ implementation to check if N
// is a Tcefrep number
#include <bits/stdc++.h>
using namespace std;

// Iterative function to
// reverse digits of num
int reverse(int num)
{
    int rev_num = 0;
    while(num > 0)
    {
        rev_num = rev_num*10 + num%10;
        num = num/10;
    }
    return rev_num;
}

// Function to calculate sum of
// all proper divisors
// num --> given natural number
int properDivSum(int num)
{
    // Final result of summation of divisors
    int result = 0;

    // find all divisors which divides 'num'
    for (int i=2; i<=sqrt(num); i++)
    {
        // if 'i' is divisor of 'num'
        if (num%i==0)
        {
            // if both divisors are same then add
            // it only once else add both
            if (i==(num/i))
                result += i;
            else
                result += (i + num/i);
        }
    }

    // Add 1 to the result as 1 is also a divisor
    return (result + 1);
}

bool isTcefrep(int n)
{
    return properDivSum(n) == reverse(n);
}

// Driver Code
int main()
{
    // Given Number N
    int N = 6;

    // Function Call
    if (isTcefrep(N))
        cout << "Yes";
    else
        cout << "No";
    return 0;
}
```

## Java

```java
// Java program for above approach
class GFG{

// Iterative function to
// reverse digits of num
static int reverse(int num)
{
    int rev_num = 0;
    while(num > 0)
    {
        rev_num = rev_num * 10 + num % 10;
        num = num / 10;
    }
    return rev_num;
}

// Function to calculate sum of
// all proper divisors
// num --> given natural number
static int properDivSum(int num)
{
    // Final result of summation of divisors
    int result = 0;

    // find all divisors which divides 'num'
    for (int i = 2; i<= Math.sqrt(num); i++)
    {
        // if 'i' is divisor of 'num'
        if (num % i == 0)
        {
            // if both divisors are same then add
            // it only once else add both
            if (i == (num / i))
                result += i;
            else
                result += (i + num / i);
        }
    }

    // Add 1 to the result as 1
    // is also a divisor
    return (result + 1);
}

static boolean isTcefrep(int n)
{
    return properDivSum(n) == reverse(n);
}

// Driver Code
public static void main(String[] args)
{
    int N = 6;

    // Function Call
    if (isTcefrep(N))
        System.out.print("Yes");
    else
        System.out.print("No");
}
}
```

## Python 3

```python
# Python3 implementation to check if N
# is a Tcefrep number
import math

# Iterative function to
# reverse digits of num
def reverse(num):
    rev_num = 0
    while(num > 0):
        rev_num = rev_num * 10 + num % 10
        num = num // 10

    return rev_num

# Function to calculate sum of
# all proper divisors
# num --> given natural number
def properDivSum(num):

    # Final result of summation of divisors
    result = 0

    # find all divisors which divides 'num'
    for i in range(2, (int)(math.sqrt(num)) + 1):

        # if 'i' is divisor of 'num'
        if (num % i == 0):

            # if both divisors are same then add
            # it only once else add both
            if (i == (num // i)):
                result += i
            else:
                result += (i + num / i)

    # Add 1 to the result as 1 is also a divisor
    return (result + 1)

def isTcefrep(n):
    return properDivSum(n) == reverse(n)

# Driver Code

# Given Number N
N = 6

# Function Call
if(isTcefrep(N)):
    print("Yes")
else:
    print("No")
```

## C#

```csharp
// C# program for above approach
using System;
class GFG{

// Iterative function to
// reverse digits of num
static int reverse(int num)
{
    int rev_num = 0;
    while(num > 0)
    {
        rev_num = rev_num * 10 + num % 10;
        num = num / 10;
    }
    return rev_num;
}

// Function to calculate sum of
// all proper divisors
// num --> given natural number
static int properDivSum(int num)
{
    // Final result of summation of divisors
    int result = 0;

    // find all divisors which divides 'num'
    for (int i = 2; i<= Math.Sqrt(num); i++)
    {
        // if 'i' is divisor of 'num'
        if (num % i == 0)
        {
            // if both divisors are same then add
            // it only once else add both
            if (i == (num / i))
                result += i;
            else
                result += (i + num / i);
        }
    }

    // Add 1 to the result as 1
    // is also a divisor
    return (result + 1);
}

static bool isTcefrep(int n)
{
    return properDivSum(n) == reverse(n);
}

// Driver Code
public static void Main()
{
    int N = 6;

    // Function Call
    if (isTcefrep(N))
        Console.Write("Yes");
    else
        Console.Write("No");
}
}
```

## JavaScript

```javascript
<script>
// Javascript program for above approach

// Iterative function to
// reverse digits of num
function reverse(num) {
    let rev_num = 0;
    while (num > 0) {
        rev_num = rev_num * 10 + num % 10;
        num = parseInt(num / 10);
    }
    return rev_num;
}

// Function to calculate sum of
// all proper divisors
// num --> given natural number
function properDivSum(num) {
    // Final result of summation of divisors
    let result = 0;

    // find all divisors which divides 'num'
    for (i = 2; i <= Math.sqrt(num); i++) {
        // if 'i' is divisor of 'num'
        if (num % i == 0) {
            // if both divisors are same then add
            // it only once else add both
            if (i == (num / i))
                result += i;
            else
                result += (i + num / i);
        }
    }

    // Add 1 to the result as 1
    // is also a divisor
    return (result + 1);
}

function isTcefrep(n) {
    return properDivSum(n) == reverse(n);
}

// Driver Code
let N = 6;

// Function Call
if (isTcefrep(N))
    document.write("Yes");
else
    document.write("No");
</script>
```

**输出:**

```
Yes
```

**时间复杂度:** O(n²)

**参考:** [http://www.numbersaplenty.com/set/tcefrep_number/](http://www.numbersaplenty.com/set/tcefrep_number/)