# 从两个数组的单个平均值和组合平均值中找出两个数组中元素数量的比率

> 原文：[https://www.geeksforgeeks.org/find-the-ratio-of-number-of-elements-in-two-arrays-from-their-individual-and-combined-average/](https://www.geeksforgeeks.org/find-the-ratio-of-number-of-elements-in-two-arrays-from-their-individual-and-combined-average/)

## 问题描述

给定两个数组中元素的平均值分别为`a`和`b`，它们的组合平均值为`c`，任务是找出两个数组中元素数量的比率。

## 示例

```
Input:  a = 2, b = 8, c = 5
Output: 1:1

Input: a = 4, b = 10, c = 6
Output: 2:1
```

## 进场思路

*   设两个数组中的元素个数分别为`x`和`y`。
*   所以组合数组中所有元素的和就是`(a*x + b*y)`。
*   组合数组中的元素总数为`(x + y)`，让`f = x / y`。
*   所以，`(a*x + b*y) / (x + y) = c`
    `(a*f + b) / (f + 1) = c`
    `f * (c - a) = b - c`
    所以，`f = (b - c) / (c - a)`
*   这是我们需要的答案。

以下是上述方法的实现：

## C++

```cpp
// C++ program to Find the Ratio
// of number of Elements in two Arrays
// from their individual and combined Average

#include <bits/stdc++.h>
using namespace std;

// C++ function to find the ratio
// of number of array elements
void FindRatio(int a, int b, int c)
{

    int up = abs(b - c);
    int down = abs(c - a);

    // calculating GCD of them
    int g = __gcd(up, down);

    // make neumarator and
    // denominator coprime
    up /= g;
    down /= g;

    cout << up << ":"
         << down << "\n";
}

// Driver Code
int main()
{

    int a = 4, b = 10, c = 6;

    FindRatio(a, b, c);

    return 0;
}
```

## Java

```java
// Java program to Find the Ratio
// of number of Elements in two Arrays
// from their individual and combined Average
class GFG
{
    static int gcd(int a, int b)
    {
        if (b == 0)
            return a;
        return gcd(b, a % b);

    }

    // function to find the ratio
    // of number of array elements
    static void FindRatio(int a, int b, int c)
    {
        int up = Math.abs(b - c);
        int down = Math.abs(c - a);

        // calculating GCD of them
        int g = gcd(up, down);

        // make neumarator and
        // denominator coprime
        up /= g;
        down /= g;

        System.out.println(up + ":" + down);
    }

    // Driver Code
    public static void main (String[] args)
    {
        int a = 4, b = 10, c = 6;

        FindRatio(a, b, c);
    }
}

// This code is contributed by AnkitRai01
```

## Python 3

```python
# Python3 program to Find the Ratio
# of number of Elements in two Arrays
# from their individual and combined Average
from math import gcd

# function to find the ratio
# of number of array elements
def FindRatio(a, b, c):

    up = abs(b - c)
    down = abs(c - a)

    # calculating GCD of them
    g = gcd(up, down)

    # make neumarator and
    # denominator coprime
    up //= g
    down //= g

    print(up,":", down)

# Driver Code
a = 4
b = 10
c = 6

FindRatio(a, b, c)

# This code is contributed by Mohit Kumar
```

## C#

```csharp
// C# program to Find the Ratio
// of number of Elements in two Arrays
// from their individual and combined Average
using System;

class GFG
{
    static int gcd(int a, int b)
    {
        if (b == 0)
            return a;
        return gcd(b, a % b);

    }

    // function to find the ratio
    // of number of array elements
    static void FindRatio(int a, int b, int c)
    {
        int up = Math.Abs(b - c);
        int down = Math.Abs(c - a);

        // calculating GCD of them
        int g = gcd(up, down);

        // make neumarator and
        // denominator coprime
        up /= g;
        down /= g;

        Console.WriteLine(up + ":" + down);
    }

    // Driver Code
    public static void Main (String []args)
    {
        int a = 4, b = 10, c = 6;

        FindRatio(a, b, c);
    }
}

// This code is contributed by Arnab Kundu
```

## JavaScript

```javascript
<script>
// Javascript program to Find the Ratio
// of number of Elements in two Arrays
// from their individual and combined Average

// Javascript function to find the ratio
// of number of array elements
function FindRatio(a, b, c)
{

    let up = Math.abs(b - c);
    let down = Math.abs(c - a);

    // calculating GCD of them
    let g = gcd(up, down);

    // make neumarator and
    // denominator coprime
    up = parseInt(up / g);
    down = parseInt(down / g);

    document.write(up + ":"
         + down + "<br>");
}

function gcd(a, b)
{
  if (b == 0)
      return a;
  return gcd(b, a % b);

}

// Driver Code

    let a = 4, b = 10, c = 6;

    FindRatio(a, b, c);

</script>
```

**输出：**

```
2:1
```