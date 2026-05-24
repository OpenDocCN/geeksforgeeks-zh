# 检查 N 是否为居中的非十边形数字的程序

> 原文：[https://www.geeksforgeeks.org/program-to-check-if-n-is-a-centered-nonadecagonal-number/](https://www.geeksforgeeks.org/program-to-check-if-n-is-a-centered-nonadecagonal-number/)

给定一个整数 `N`，任务是检查它是否是一个[中心非十边形数](https://www.geeksforgeeks.org/centered-nonadecagonal-number/)。

> **【居中的非十边形数字】** 表示在连续的非十边形（19 边多边形）图层中，位于中心的一个点和围绕它的其他点。前几个居中的非十边形数字是 1、20、58、115、191、286。

**例：**

> **输入：** `N = 20`
> **输出：** 是
> **说明：**
> 20 是第二个居中的非十边形数。
> **输入：** `38`
> **输出：** 否
> **说明：**
> 38 不是一个居中的非十边形数。

## 方法

为了解决上面提到的问题，我们必须知道中心非十边形数的第 K 项给出为：
`K^{th} Term = \frac {19*N^{2} - 19*N + 2}{2}`

因为我们必须检查给定的数是否可以表示为中心非十边形数。这可以通过将公式推广到以下形式来检查：

> => `N = \frac {19 * k ^ {2} - 19 * k + 2} {2}`
> => `K = \frac{19 + \sqrt{152 * N + 209}} {38}`

最后，用这个公式检查计算值，如果它是一个整数，那么就意味着 `N` 是一个居中的非十边形数。

以下是上述方法的实现：

## C++

```cpp
// C++ implementation to check that
// a number is a Centered
// nonadecagonal number or not

#include <bits/stdc++.h>
using namespace std;

// Function to check that the
// number is a Centered
// nonadecagonal number
bool isCenterednonadecagonal(int N)
{
    float n = (19
               + sqrt(152 * N + 209))
              / 38;

    // Condition to check if the
    // number is a Centered
    // nonadecagonal number
    return (n - (int)n) == 0;
}

// Driver Code
int main()
{
    int n = 20;

    // Function call
    if (isCenterednonadecagonal(n)) {
        cout << "Yes";
    }
    else {
        cout << "No";
    }
    return 0;
}
```

## Java

```java
// Java implementation to check that
// a number is a Centered
// nonadecagonal number or not
class GFG{

// Function to check that the
// number is a Centered
// nonadecagonal number
static boolean isCenterednonadecagonal(int N)
{
    float n = (float)((19 + Math.sqrt(152 * N +
                                      209)) / 38);

    // Condition to check if the
    // number is a Centered
    // nonadecagonal number
    return (n - (int)n) == 0;
}

// Driver Code
public static void main(String[] args)
{
    int n = 20;

    // Function call
    if (isCenterednonadecagonal(n))
    {
        System.out.print("Yes");
    }
    else
    {
        System.out.print("No");
    }
}
}

// This code is contributed by sapnasingh4991
```

## Python 3

```python
# Python3 implementation to check that
# a number is a Centered
# nonadecagonal number or not
import math

# Function to check that the
# number is a Centered
# nonadecagonal number
def isCenterednonadecagonal(N):

    n = (19 + math.sqrt(152 * N +
                        209)) / 38;

    # Condition to check if the
    # number is a Centered
    # nonadecagonal number
    return (n - int(n)) == 0;

# Driver Code
n = 20;

# Function call
if (isCenterednonadecagonal(n)):
    print("Yes");

else:
    print("No");

# This code is contributed by Code_Mech
```

## C#

```csharp
// C# implementation to check that
// a number is a Centered
// nonadecagonal number or not
using System;
class GFG{

// Function to check that the
// number is a Centered
// nonadecagonal number
static bool isCenterednonadecagonal(int N)
{
    float n = (float)((19 + Math.Sqrt(152 * N +
                                      209)) / 38);

    // Condition to check if the
    // number is a Centered
    // nonadecagonal number
    return (n - (int)n) == 0;
}

// Driver Code
public static void Main()
{
    int n = 20;

    // Function call
    if (isCenterednonadecagonal(n))
    {
        Console.Write("Yes");
    }
    else
    {
        Console.Write("No");
    }
}
}

// This code is contributed by Nidhi_biet
```

## JavaScript

```javascript
<script>

// Javascript implementation to check that
// a number is a Centered
// nonadecagonal number or not

// Function to check that the
// number is a Centered
// nonadecagonal number
function isCenterednonadecagonal(N)
{
    var n = (19
               + Math.sqrt(152 * N + 209))
              / 38;

    // Condition to check if the
    // number is a Centered
    // nonadecagonal number
    return (n - parseInt(n)) == 0;
}

// Driver Code
var n = 20;

// Function call
if (isCenterednonadecagonal(n)) {
    document.write("Yes");
}
else {
    document.write("No");
}

</script>
```

**输出：**

```
Yes
```

**时间复杂度：** `O(1)`
**辅助空间：** `O(1)`