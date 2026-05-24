# 六角体编号

> 原文: [https://www.geeksforgeeks.org/hexacontatetragon-numbers/](https://www.geeksforgeeks.org/hexacontatetragon-numbers/)

给定一个数字 `N`，任务是找到第 `N` 个六角数。

> 六角数是一类图形数。它有一个 64 边的多边形，叫做六角四边形。第 `N` 个六角点的个数是 64 个点，所有其他点都被一个共同的角包围并形成一个图案。前几个六角数是 `1，64，189，376，625，936，…`

**例:**

> **输入:** `N = 2`
> **输出:** `64`
> **说明:**
> 第二个六角数为 `64`。
> **输入:** `N = 3`
> **输出:** `189`

**方法:** 第 `N` 个六角数由公式给出:

*   s 边多边形的第 n 项 = ![\frac{((s-2)n^2 - (s-4)n)}{2}](img/e1b7be7ec1f82453b47cd0c23edff33f.png "Rendered by QuickLaTeX.com")
*   因此 64 边多边形的第 n 项是
> ![T_n =\frac{((64-2)n^2 - (64-4)n)}{2} =\frac{(62n^2 - 60n)}{2}](img/34ba3a0d532cdff1b6a12f53002f74b4.png "Rendered by QuickLaTeX.com")

以下是上述方法的实现:

## C++

```cpp
// C++ implementation for above approach
#include <bits/stdc++.h>
using namespace std;

// Function to Find the
// Nth Hexacontatetragon Number
int HexacontatetragonNum(int n)
{
    return (62 * n * n - 60 * n) / 2;
}

// Driver Code
int main()
{
    int n = 3;
    cout << HexacontatetragonNum(n);

    return 0;
}
```

## Java

```java
// Java program to find N-th
// Hexacontatetragon number
class GFG{

// Function to find the nth
// Hexacontatetragon number
static int HexacontatetragonNum(int n)
{
    return (62 * n * n - 60 * n) / 2;
}

// Driver code
public static void main(String[] args)
{
    int n = 3;
    System.out.print(HexacontatetragonNum(n));
}
}

// This code is contributed by shubham
```

## Python 3

```python
# Python3 implementation for above approach

# Function to Find the
# Nth Hexacontatetragon Number
def HexacontatetragonNum(n):
    return (62 * n * n - 60 * n) // 2

# Driver Code
n = 3
print(HexacontatetragonNum(n))

# This code is contributed by Code_Mech
```

## C#

```csharp
// C# program to find N-th
// Hexacontatetragon number
using System;
class GFG{

// Function to find the nth
// Hexacontatetragon number
static int HexacontatetragonNum(int n)
{
    return (62 * n * n - 60 * n) / 2;
}

// Driver code
public static void Main()
{
    int n = 3;
    Console.Write(HexacontatetragonNum(n));
}
}

// This code is contributed by Code_Mech
```

## JavaScript

```javascript
<script>
// Javascript program to find N-th
// Hexacontatetragon number

// Function to find the nth
// Hexacontatetragon number
function HexacontatetragonNum(n) {
    return (62 * n * n - 60 * n) / 2;
}

// Driver code
let n = 3;
document.write(HexacontatetragonNum(n));

// This code contributed by aashish1995
</script>
```

**Output:**

```
189
```

**时间复杂度:** `O(1)`

**参考资料:** [https://en.wikipedia.org/wiki/Hexacontatetragon](https://en.wikipedia.org/wiki/Hexacontatetragon)