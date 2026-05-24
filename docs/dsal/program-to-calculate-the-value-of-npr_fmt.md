# 计算 nPr 值的程序

> 原文：[https://www.geeksforgeeks.org/program-to-calculate-the-value-of-npr/](https://www.geeksforgeeks.org/program-to-calculate-the-value-of-npr/)

给定两个数字 `n` 和 `r`，任务是找到 `nPr` 的值。
`nPr` 代表 `n` [排列](https://www.geeksforgeeks.org/permutation-and-combination/) `r`，计算为 `n!/(n-r)!`。排列是指将给定集合的所有成员排列成一个序列的过程。一组 `n` 个元素上的排列数由 `n!` 给出，其中 `!` 代表阶乘。

```
<sup>nP</sup><sub><sup>r = n! / (n - r)!</sup></sub>
```

**程序：**

## C++

```cpp
// CPP program to calculate nPr
#include<bits/stdc++.h>
using namespace std;

int fact(int n)
{
    if (n <= 1)
        return 1;
    return n * fact(n - 1);
}

int nPr(int n, int r)
{
    return fact(n) / fact(n - r);
}

// Driver code
int main()
{
    int n = 5;
    int r = 2;

    cout << n << "P" << r << " = " << nPr(n, r);
}

// This code is contributed by
// Surendra_Gangwar
```

## Java

```java
// Java program to calculate nPr

import java.util.*;

public class GFG {

    static int fact(int n)
    {
        if (n <= 1)
            return 1;
        return n * fact(n - 1);
    }

    static int nPr(int n, int r)
    {
        return fact(n) / fact(n - r);
    }

    public static void main(String args[])
    {
        int n = 5;
        int r = 2;

        System.out.println(n + "P" + r + " = "
                           + nPr(n, r));
    }
}
```

## Python 3

```python
# Python3 program to calculate nPr
import math
def fact(n):
    if (n <= 1):
        return 1

    return n * fact(n - 1)

def nPr(n, r):

    return math.floor(fact(n) /
                fact(n - r))

# Driver code
n = 5
r = 2

print(n, "P", r, "=", nPr(n, r))

# This code contributed by Rajput-Ji
```

## C#

```csharp
// C# program to calculate nPr
using System;

class GFG
{

    static int fact(int n)
    {
        if (n <= 1)
            return 1;
        return n * fact(n - 1);
    }

    static int nPr(int n, int r)
    {
        return fact(n) / fact(n - r);
    }

    public static void Main()
    {
        int n = 5;
        int r = 2;

        Console.WriteLine(n + "P" + r + " = "
                        + nPr(n, r));
    }
}

/* This code contributed by PrinciRaj1992 */
```

## PHP

```php
<?php
// PHP program to calculate nPr
function fact($n)
{
    if ($n <= 1)
        return 1;

    return $n * fact($n - 1);
}

function nPr($n, $r)
{
    return floor(fact($n) /
                 fact($n - $r));
}

// Driver code
$n = 5;
$r = 2;

echo $n, "P", $r, " = ", nPr($n, $r);

// This code is contributed by Ryuga
?>
```

## JavaScript

```javascript
// Javascript program to calculate nPr
function fact(n)
{
    if (n <= 1)
        return 1;

    return n * fact(n - 1);
}

function nPr(n, r)
{
    return Math.floor(fact(n) /
                fact(n - r));
}

// Driver code
let n = 5;
let r = 2;

document.write(n, "P", r, " = ", nPr(n, r));

// This code is contributed by gfgking
```

**输出：**

```
5P2 = 20
```

**对 `nPr` 的多个查询进行优化**
如果对 `nPr` 有多个查询，我们可以预先计算阶乘值，并在每次调用时使用相同的值。这将避免反复计算相同的阶乘值。