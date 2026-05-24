# 在一张桌子的两边安排 2*N 个人，X 和 Y 个人相对的方式数量

> 原文：[https://www.geeksforgeeks.org/number-of-ways-to-arrange-2n-persons-on-the-two-sides-of-a-table-with-x-and-y-persons-on-opposite-sides/](https://www.geeksforgeeks.org/number-of-ways-to-arrange-2n-persons-on-the-two-sides-of-a-table-with-x-and-y-persons-on-opposite-sides/)

给定三个整数 `N`、`X` 和 `Y`。任务是找到将 `2*N` 人沿桌子两侧排列的方法数量，每侧的椅子数量为 `N` 个，使得 `X` 人在一侧，`Y` 人在另一侧。
**注：** `X` 和 `Y` 均小于或等于 `N`。

**例：**

> **输入：** `N = 5`，`X = 4`，`Y = 2`
> **输出：** `57600`
> **说明：**
> 总人数 10 人。一边 `X` 人，另一边 `Y` 人，则剩下 `10–4–2 = 4` 人。我们可以通过 $\binom{4}{1}$ 方式选择其中 `5–4 = 1` 人坐在一边，其余人员将自动坐在另一边。每一面的布置都是在 `5!` 方法。途径数为 $\binom{4}{1} \cdot 5! \cdot 5!$。
> **输入：** `N = 3`，`X = 1`，`Y = 2`
> **输出：** `108`

**进场：**
总人数 `2*N`，让我们称双方为 `A` 和 `B`，`A` 面 `X` 人，`B` 面 `Y` 人，则剩下 `2 * N–X–Y` 人。我们可以通过 $\binom{2*N - X - Y}{N-X}$ 的方式为 `A` 面选择其中的 `N-X` 个，剩下的人会自动坐在 `B` 面的另一边，每一面的排列都是在 `N!` 方法。沿桌子两边安排 `2*N` 人的方式数量为 $\binom{2*N - X - Y}{N-X} \cdot N! \cdot N!$。

以下是上述方法的实施：

## C++

```cpp
#include <bits/stdc++.h>
using namespace std;

// Function to find factorial of a number
int factorial(int n)
{
    if (n <= 1)
        return 1;
    return n * factorial(n - 1);
}

// Function to find nCr
int nCr(int n, int r)
{
    return factorial(n) / (factorial(n - r) * factorial(r));
}

// Function to find the number of ways to arrange 2*N persons
int NumberOfWays(int n, int x, int y)
{
    return nCr(2*n-x-y, n-x) * factorial(n) * factorial(n);
}

// Driver code
int main()
{
    int n = 5, x = 4, y = 2;

    // Function call
    cout << NumberOfWays(n, x, y);

    return 0;
}
```

## Java

```java
// Java implementation for the above approach
import java.util.*;
import java.lang.*;
import java.io.*;

class GFG
{

    // Function to returns factorial of n
    static int factorial(int n)
    {
        if (n <= 1)
            return 1;
        return n * factorial(n - 1);
    }

    // Function to find nCr
    static int nCr(int n, int r)
    {
        return factorial(n) / (factorial(n - r) *
                               factorial(r));
    }

    // Function to find the number of ways
    // to arrange 2*N persons
    static int NumberOfWays(int n, int x, int y)
    {
        return nCr(2 * n - x - y, n - x) *
               factorial(n) * factorial(n);
    }

    // Driver code
    public static void main (String[] args)
                 throws java.lang.Exception
    {
        int n = 5, x = 4, y = 2;

        // Function call
        System.out.println(NumberOfWays(n, x, y));        
    }
}

// This code is contributed by Nidhiva
```

## Python 3

```python
# Python3 implementation for the above approach

# Function to find factorial of a number
def factorial(n):

    if (n <= 1):
        return 1;
    return n * factorial(n - 1);

# Function to find nCr
def nCr(n, r):

    return (factorial(n) /
           (factorial(n - r) * factorial(r)));

# Function to find the number of ways
# to arrange 2*N persons
def NumberOfWays(n, x, y):

    return (nCr(2 * n - x - y, n - x) *
            factorial(n) * factorial(n));

# Driver code
n, x, y = 5, 4, 2;

# Function call
print(int(NumberOfWays(n, x, y)));

# This code is contributed by PrinciRaj1992
```

## C#

```csharp
// C# implementation for the above approach
using System;

class GFG
{

    // Function to returns factorial of n
    static int factorial(int n)
    {
        if (n <= 1)
            return 1;
        return n * factorial(n - 1);
    }

    // Function to find nCr
    static int nCr(int n, int r)
    {
        return factorial(n) / (factorial(n - r) *
                               factorial(r));
    }

    // Function to find the number of ways
    // to arrange 2*N persons
    static int NumberOfWays(int n, int x, int y)
    {
        return nCr(2 * n - x - y, n - x) *
            factorial(n) * factorial(n);
    }

    // Driver code
    public static void Main(String[] args)
    {
        int n = 5, x = 4, y = 2;

        // Function call
        Console.WriteLine(NumberOfWays(n, x, y));        
    }
}

// This code is contributed by Princi Singh
```

## PHP

```php
<?php
// PHP implementation for the above approach

// Function to find factorial of a number
function factorial($n)
{
    if ($n <= 1)
        return 1;
    return $n * factorial($n - 1);
}

// Function to find nCr
function nCr($n, $r)
{
    return factorial($n) / (factorial($n - $r) *
                            factorial($r));
}

// Function to find the number of ways
// to arrange 2*N persons
function NumberOfWays($n, $x, $y)
{
    return nCr(2 * $n - $x - $y, $n - $x) *
           factorial($n) * factorial($n);
}

// Driver code
$n = 5;
$x = 4;
$y = 2;

// Function call
echo (NumberOfWays($n, $x, $y));

// This code is contributed by Naman_garg.
?>
```

## JavaScript

```javascript
<script>

// JavaScript implementation for the above approach
// Function to returns factorial of n
    function factorial(n) {
        if (n <= 1)
            return 1;
        return n * factorial(n - 1);
    }

    // Function to find nCr
    function nCr(n , r) {
        return factorial(n) / (factorial(n - r) * factorial(r));
    }

    // Function to find the number of ways
    // to arrange 2*N persons
    function NumberOfWays(n , x , y) {
        return nCr(2 * n - x - y, n - x) * factorial(n) * factorial(n);
    }

    // Driver code

        var n = 5, x = 4, y = 2;

        // Function call
        document.write(NumberOfWays(n, x, y));

// This code contributed by Rajput-Ji

</script>
```

**Output：**

```