# 找出三个小于或等于 N 的整数，使它们的 LCM 最大

> 原文: [https://www.geeksforgeeks.org/find-three-integers-less-than-or-equal-to-n-such-that-their-lcm-is-maximum/](https://www.geeksforgeeks.org/find-three-integers-less-than-or-equal-to-n-such-that-their-lcm-is-maximum/)

给定一个数字 `N` (>=3)。任务是找到三个整数 (<=N) 使得这三个整数的 LCM 最大。

**示例:**

```
Input: N = 3
Output: 1 2 3

Input: N = 5
Output: 3 4 5
```

**方法:** 由于任务是最大化 LCM，所以如果所有三个数字没有任何共同因素，那么 LCM 将是这三个数字的乘积，并且将是最大值。

> *   如果 `n` 是一个奇数，那么答案将是 `n, n-1, n-2`。
> *   如果 `n` 是一个偶数，
>     1.  如果 `n` 和 `n-3` 的 `gcd` 是 1，答案是 `n, n-1, n-3`。
>     2.  否则，答案将是 `n-1, n-2, n-3`。

以下是上述方法的实现:

## C++

```cpp
// CPP Program to find three integers
// less than N whose LCM is maximum
#include <bits/stdc++.h>
using namespace std;

// function to find three integers
// less than N whose LCM is maximum
void MaxLCM(int n)
{
    // if n is odd
    if (n % 2 != 0)
        cout << n << " " << (n - 1) << " " << (n - 2);

    // if n is even and n, n-3 gcd is 1
    else if (__gcd(n, (n - 3)) == 1)
        cout << n << " " << (n - 1) << " " << (n - 3);

    else
        cout << (n - 1) << " " << (n - 2) << " " << (n - 3);
}

// Driver code
int main()
{
    int n = 12;

    // function call
    MaxLCM(n);

    return 0;
}
```

## Java

```java
// Java Program to find three integers
// less than N whose LCM is maximum

import java.io.*;

class GFG {
   // Recursive function to return gcd of a and b
static int __gcd(int a, int b)
{
    // Everything divides 0 
    if (a == 0)
       return b;
    if (b == 0)
       return a;

    // base case
    if (a == b)
        return a;

    // a is greater
    if (a > b)
        return __gcd(a-b, b);
    return __gcd(a, b-a);
}

// function to find three integers
// less than N whose LCM is maximum
static void MaxLCM(int n)
{
    // if n is odd
    if (n % 2 != 0)
        System.out.print(n + " " + (n - 1) + " " + (n - 2));

    // if n is even and n, n-3 gcd is 1
    else if (__gcd(n, (n - 3)) == 1)
        System.out.print( n + " " +(n - 1)+ " " + (n - 3));

    else
        System.out.print((n - 1) + " " + (n - 2) + " " + (n - 3));
}

// Driver code
public static void main (String[] args) {
    int n = 12;

    // function call
    MaxLCM(n);
    }
}
// This code is contributed by anuj_67..
```

## Python 3

```python
# Python 3 Program to find three integers
# less than N whose LCM is maximum
from math import gcd

# function to find three integers
# less than N whose LCM is maximum
def MaxLCM(n) :

    # if n is odd
    if (n % 2 != 0) :
        print(n, (n - 1), (n - 2))

    # if n is even and n, n-3 gcd is 1
    elif (gcd(n, (n - 3)) == 1) :
        print(n, (n - 1), (n - 3))

    else :
        print((n - 1), (n - 2), (n - 3))

# Driver Code
if __name__ == "__main__" :

    n = 12

    # function call
    MaxLCM(n)

# This code is contributed by Ryuga
```

## C#

```csharp
// C# Program to find three integers
// less than N whose LCM is maximum

using System;

class GFG {
// Recursive function to return gcd of a and b
static int __gcd(int a, int b)
{
    // Everything divides 0
    if (a == 0)
    return b;
    if (b == 0)
    return a;

    // base case
    if (a == b)
        return a;

    // a is greater
    if (a > b)
        return __gcd(a-b, b);
    return __gcd(a, b-a);
}

// function to find three integers
// less than N whose LCM is maximum
static void MaxLCM(int n)
{
    // if n is odd
    if (n % 2 != 0)
        Console.Write(n + " " + (n - 1) + " " + (n - 2));

    // if n is even and n, n-3 gcd is 1
    else if (__gcd(n, (n - 3)) == 1)
        Console.Write( n + " " +(n - 1)+ " " + (n - 3));

    else
        Console.Write((n - 1) + " " + (n - 2) + " " + (n - 3));
}

// Driver code
public static void Main () {
    int n = 12;

    // function call
    MaxLCM(n);
    }
}
// This code is contributed by anuj_67..
```

## PHP

```php
<?php
// PHP Program to find three integers
// less than N whose LCM is maximum

// Recursive function to return
// gcd of a and b
function __gcd($a, $b)
{
    // Everything divides 0
    if ($a == 0)
        return $b;
    if ($b == 0)
        return $a;

    // base case
    if ($a == $b)
        return $a;

    // a is greater
    if ($a > $b)
        return __gcd($a - $b, $b);
    return __gcd($a, $b - $a);
} 

// function to find three integers
// less than N whose LCM is maximum
function MaxLCM($n)
{
    // if n is odd
    if ($n % 2 != 0)
        echo $n , " " , ($n - 1) ,
                  " " , ($n - 2);

    // if n is even and n, n-3 gcd is 1
    else if (__gcd($n, ($n - 3)) == 1)
        echo $n , " " , ($n - 1),
                  " " , ($n - 3);

    else
        echo ($n - 1) , " " , ($n - 2),
                        " " , ($n - 3);
}

// Driver code
$n = 12;

// function call
MaxLCM($n);

// This code is contributed by Sachin
?>
```

## JavaScript

```javascript
<script>

// JavaScript Program to find three integers
// less than N whose LCM is maximum

    // Recursive function to return gcd of a and b
    function __gcd(a , b)
    {
        // Everything divides 0
        if (a == 0)
            return b;
        if (b == 0)
            return a;

        // base case
        if (a == b)
            return a;

        // a is greater
        if (a > b)
            return __gcd(a - b, b);
        return __gcd(a, b - a);
    }

    // function to find three integers
    // less than N whose LCM is maximum
    function MaxLCM(n) {
        // if n is odd
        if (n % 2 != 0)
            document.write(n + " " + (n - 1) + " " + (n - 2));

        // if n is even and n, n-3 gcd is 1
        else if (__gcd(n, (n - 3)) == 1)
            document.write(n + " " + (n - 1) + " " + (n - 3));

        else
            document.write((n - 1) + " " + (n - 2) + " " + (n - 3));
    }

    // Driver code

        var n = 12;

        // function call
        MaxLCM(n);

// This code contributed by Rajput-Ji

</script>
```

**Output:**

```
11 10 9
```