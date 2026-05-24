# 检查 N 是否为 icosidigonal 数的程序

> 原文：[https://www.geeksforgeeks.org/program-to-check-if-n-is-a-icosidigonal-number/](https://www.geeksforgeeks.org/program-to-check-if-n-is-a-icosidigonal-number/)

给定一个整数 `N`，任务是检查它是否是一个 [icosidigonal 数](https://www.geeksforgeeks.org/Icosidigonal-number/)。如果数字 `N` 是 icosidigonal 数，则打印“是”，否则打印“否”。

> **icosidigonal 数**：
> 多边形数有很多种，取决于它们的边数。在数学中，有许多多边形数，Icosidigonal 数就是其中之一，这些数对应 22 边多边形（**icosidigon**）。一个 **Icosidigonal 数**属于多边形数的范畴。它们有一个共同的模式，即点被排列成第 `n` 个嵌套的 Icosidigon 图案。
> 前几个 Icosidigonal 数字是 1，22，63，124，205，306…

## 示例

> **输入：** `N = 22`
> **输出：** 是
> **说明：**
> 第二个 Icosidigonal 数为 22。
>
> **输入：** `N = 30`
> **输出：** 否

## 方法

1.  Icosidigonal 数的第 `K` 项公式为：
    ![K^{th} Term = \frac{20*K^{2} - 18*K}{2}](img/4d585eda3c53d3aad72fe729a138ffbf.png "Rendered by QuickLaTeX.com")

2.  因为我们必须检查给定的数字是否可以表示为 Icosidigonal 数。这可以通过以下方式进行检查：
    > `N = (20*K^2 - 18*K) / 2`
    > `K = (18 + sqrt(160*N + 324)) / 40`

3.  如果使用上述公式计算的 `K` 的值是整数，那么 `N` 是一个 Icosidigonal 数。

4.  否则 `N` 不是一个 Icosidigonal 数。

下面是上述方法的实现：

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to check if the number N
// is a Icosidigonal number
bool isIcosidigonal(int N)
{
    float n
        = (18 + sqrt(160 * N + 324))
          / 40;

    // Condition to check if the
    // number is a Icosidigonal number
    return (n - (int)n) == 0;
}

// Driver Code
int main()
{
    // Given Number
    int N = 22;

    // Function call
    if (isIcosidigonal(N)) {
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
// Java program for the above approach
class GFG{

// Function to check if the number N
// is a icosidigonal number
static boolean isIcosidigonal(int N)
{
    float n = (float) ((18 + Math.sqrt(160 * N +
                                       324)) / 40);

    // Condition to check if the number
    // is a icosidigonal number
    return (n - (int)n) == 0;
}

// Driver Code
public static void main(String[] args)
{

    // Given number
    int N = 22;

    // Function call
    if (isIcosidigonal(N))
    {
        System.out.print("Yes");
    }
    else
    {
        System.out.print("No");
    }
}
}

// This code is contributed by Amit Katiyar
```

## Python

```python
# Python3 program for the above approach
import numpy as np

# Function to check if the number N
# is a icosidigonal number
def isIcosidigonal(N):

    n = (18 + np.sqrt(160 * N + 324)) / 40

    # Condition to check if N
    # is a icosidigonal number
    return (n - int(n)) == 0

# Driver Code
N = 22

# Function call
if (isIcosidigonal(N)):
    print ("Yes")
else:
    print ("No")

# This code is contributed by PratikBasu
```

## C#

```csharp
// C# program for the above approach
using System;

class GFG{

// Function to check if the number N
// is a icosidigonal number
static bool isIcosidigonal(int N)
{
    float n = (float) ((18 + Math.Sqrt(160 * N +
                                    324)) / 40);

    // Condition to check if the number
    // is a icosidigonal number
    return (n - (int)n) == 0;
}

// Driver Code
public static void Main(string[] args)
{

    // Given number
    int N = 22;

    // Function call
    if (isIcosidigonal(N))
    {
        Console.Write("Yes");
    }
    else
    {
        Console.Write("No");
    }
}
}

// This code is contributed by rutvik_56
```

## JavaScript

```javascript
<script>

// javascript program for the above approach

// Function to check if the number N
// is a Icosidigonal number
function isIcosidigonal( N)
{
    let n
        = (18 + Math.sqrt(160 * N + 324))
          / 40;

    // Condition to check if the
    // number is a Icosidigonal number
    return (n - parseInt(n)) == 0;
}

// Driver Code

    // Given Number
    let N = 22;

    // Function call
    if (isIcosidigonal(N)) {
         document.write( "Yes");
    }
    else {
        document.write( "No");
    }

    // This code contributed by aashish1995

</script>
```

**输出：**

```
Yes
```

**时间复杂度：** `O(1)`

**辅助空间：** `O(1)`