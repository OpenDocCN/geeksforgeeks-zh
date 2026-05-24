# X = P * A + Q * B 中给定 A 和 B 的 X 的最小可能正整数值

> 原文: [https://www.geeksforgeeks.org/minimum-positive-integer-value-possible-of-x-for-given-a-and-b-in-x-pa-qb/](https://www.geeksforgeeks.org/minimum-positive-integer-value-possible-of-x-for-given-a-and-b-in-x-pa-qb/)

给定 `A` 和 `B` 的值，求方程 `X = P*A + Q*B` 中能达到的 `X` 的最小正整数值，这里 `P` 和 `Q` 可以为零，也可以是任何正整数或负整数。

## 示例

```
Input: A = 3
        B = 2
Output: 1

Input: A = 2
         B = 4 
Output: 2
```

## 解决思路

基本上我们需要找到 `P` 和 `Q`，使得 `P*A + Q*B` 是最小正整数。这个问题可以很容易地通过计算这两个数字的 GCD 来解决。

例如:

```
For A = 2 
And B = 4
Let P  = 1
And Q = 0            
X = P*A + Q*B
  = 1*2 + 0*4
  = 2 + 0
  = 2 (i.e GCD of 2 and 4)

For A = 3
and B = 2
let P = -1
And Q = 2
X = P*A + Q*B
  = -1*3 + 2*2
  = -3 + 4
  = 1 (i.e GCD of 2 and 3 )
```

以下是上述想法的实现:

### C++ 实现

```
// CPP Program to find
// minimum value of X
// in equation X = P*A + Q*B

#include <bits/stdc++.h>
using namespace std;

// Utility function to calculate GCD
int gcd(int a, int b)
{
    if (a == 0)
        return b;
    return gcd(b % a, a);
}

// Driver Code
int main()
{
    int a = 2;
    int b = 4;
    cout << gcd(a, b);
    return 0;
}
```

### Java 实现

```
// Java Program to find
// minimum value of X
// in equation X = P*A + Q*B
import java.util.*;
import java.lang.*;

class GFG {
    // utility function to calculate gcd

    public static int gcd(int a, int b)
    {
        if (a == 0)
            return b;

        return gcd(b % a, a);
    }

    // Driver Program
    public static void main(String[] args)
    {
        int a = 2;
        int b = 4;

        System.out.println(gcd(a, b));
    }
}
```

### Python 实现

```
# Python3 Program to find
# minimum value of X
# in equation X = P * A + Q * B

# Function to return gcd of a and b

def gcd(a, b):
    if a == 0:
        return b
    return gcd(b % a, a)

a = 2
b = 4
print(gcd(a, b))
```

### C# 实现

```
// C# Program to find
// minimum value of X
// in equation X = P*A + Q*B
using System;

class GFG {
    // function to get gcd of a and b
    public static int gcd(int a, int b)
    {
        if (a == 0)
            return b;

        return gcd(b % a, a);
    }

    // Driver Code
    static public void Main()
    {
        int a = 2;
        int b = 4;
        Console.WriteLine(gcd(a, b));
    }
}
```

### PHP 实现

```
// PHP Program to find
// minimum value of X
// in equation X = P*A + Q*B

<?php

// Function to return
// gcd of a and b
function gcd($a, $b)
{
    if ($a == 0)
        return $b;
    return gcd($b % $a, $a);
}

// Driver Code
$a = 2;
$b = 4;
echo gcd($a, $b);

?>
```

### JavaScript 实现

```
<script>
// javascript Program to find
// minimum value of X
// in equation X = P*A + Q*B

    // utility function to calculate gcd

    function gcd(a , b) {
        if (a == 0)
            return b;

        return gcd(b % a, a);
    }

    // Driver Program

        var a = 2;
        var b = 4;

        document.write(gcd(a, b));

// This code contributed by umadevi9616
</script>
```

**输出**

```

```