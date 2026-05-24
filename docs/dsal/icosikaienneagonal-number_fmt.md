# Icosikaiennegonal 数

> 原文: [https://www.geeksforgeeks.org/icosikaienneagonal-number/](https://www.geeksforgeeks.org/icosikaienneagonal-number/)

一个 `icosikaiennegonal` 数是一类图形数。它对应一个有 `29` 条边的多边形，称为 `icosikaienneagon`。第 `N` 个 `icosikaiennegonal` 数表示由 `29` 个点构成的图案数量，这些点共享一个公共角并层层包围。
前几个 `icosikaiennegonal` 数是：1、29、84、166……

## 找到第 N 个 `icosikaiennegonal` 数

给定一个数字 `N`，任务是找到第 `N` 个 [`icosikaiennegonal` 数](https://en.wikipedia.org/wiki/List_of_polygons)。

**举例：**

> **输入：** `N = 2`
> **输出：** 29
> **解释：**
> 第二个 `icosikaiennegonal` 数为 29。
>
> **输入：** `N = 3`
> **输出：** 84

**方法：**

在数学中，第 `N` 个 `s` 边多边形数由以下公式给出：
`Nth term of s sided polygon = ((s-2)n^2 - (s-4)n) / 2`

因此，对于 `29` 边多边形，其第 `n` 项为：
`Tn = ((29-2)n^2 - (29-4)n) / 2 = (27n^2 - 25n) / 2`

以下是上述方法的实现：

## C++

```cpp
// C++ implementation for
// above approach

#include <iostream>
using namespace std;

// Function to Find the Nth
// icosikaienneagonal Number
int icosikaienneagonalNum(int n)
{
    return (27 * n * n - 25 * n) / 2;
}

// Driver Code
int main()
{
    int n = 3;
    cout << icosikaienneagonalNum(n);

    return 0;
}
```

## Java

```java
// Java implementation for
// above approach
class GFG{

// Function to Find the Nth
// icosikaienneagonal Number
static int icosikaienneagonalNum(int n)
{
    return (27 * n * n - 25 * n) / 2;
}

// Driver Code
public static void main(String args[])
{
    int n = 3;
    System.out.print(icosikaienneagonalNum(n));
}
}

// This code is contributed by Code_Mech
```

## Python 3

```python
# Python3 implementation for
# above approach

# Function to Find the Nth
# icosikaienneagonal Number
def icosikaienneagonalNum(n):
    return (27 * n * n - 25 * n) // 2

# Driver Code

# Given N
N = 3
print(icosikaienneagonalNum(N))

# This code is contributed by Vishal Maurya
```

## C#

```csharp
// C# implementation for
// above approach
using System;
class GFG{

// Function to Find the Nth
// icosikaienneagonal Number
static int icosikaienneagonalNum(int n)
{
    return (27 * n * n - 25 * n) / 2;
}

// Driver Code
public static void Main()
{
    int n = 3;
    Console.Write(icosikaienneagonalNum(n));
}
}

// This code is contributed by Code_Mech
```

## JavaScript

```javascript
<script>
// Javascript implementation for
// above approach

    // Function to Find the Nth
    // icosikaienneagonal Number
    function icosikaienneagonalNum( n) {
        return (27 * n * n - 25 * n) / 2;
    }

    // Driver Code

    let n = 3;
    document.write(icosikaienneagonalNum(n));

// This code is contributed by Rajput-Ji
</script>
```

**输出：** 84

时间复杂度：`O(1)`
辅助空间：`O(1)`