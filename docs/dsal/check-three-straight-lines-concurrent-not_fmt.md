# 检查三条直线是否重合

> 原文: [https://www.geeksforgeeks.org/check-three-straight-lines-concurrent-not/](https://www.geeksforgeeks.org/check-three-straight-lines-concurrent-not/)

给定三线方程，
`a1x+b1y+c1=0`
`a2x+b2y+c2=0`
`a3x+b3y+c3=0`
如果三条直线通过一个点，即它们在一个点相遇，则称它们是重合的。

示例:

```
Input : a1 = 2, b1 = -3, c1 = 5
        a2 = 3, b2 = 4, c2 = -7
        a3 = 9, b3 = -5, c3 = 8
Output : Yes

Input : a1 = 2, b1 = -3, c1 = 5
        a2 = 3, b2 = 4, c2 = -7
        a3 = 9, b3 = -5, c3 = 4
Output : No
```

让
`a1x+b1y+c1=0`……(1)
`a2x+b2y+c2=0`……(2)
`a3x+b3y+c3=0`……(3)
假设方程(I)和(ii)相交于`(x1, y1)`。那么`(x1, y1)`将满足这两个方程。
因此，用[交叉乘法](https://www.quora.com/How-do-I-solve-equations-with-three-variables-by-cross-multiplication-method)的方法求解(I)和(ii)，我们得到:
`(x1/b1c2–b2c1)=(y1/c1a2–c2a1)=(1/a1b2–a2b1)`
`x1=(b1c2–b2c1)/(a1b2–a2b1)` 以及
`y1=(c1a2–c2a1)/(a1b2–a2b1)`，其中 `a1b2–a2b1 ≠ 0`
因此，线(I)和(ii)交点所需坐标为
`((b1c2–b2c1)/(a1b2–a2b1), (c1a2–c2a1)/(a1b2–a2b1))`
对于，三条线同时进行，`(x1, y1)` 也必须满足方程(3)。
所以，
`a3x+b3y+c3=0`
=>`a3((b1c2–b2c1)/(a1b2–a2b1))+b3((c1a2–c2a1)/(a1b2–a2b1))+c3=0`
=>`a3(b1c2–b2c1)+b3(c1a2–c2a1)+c3(a1b2–a2b1)=0`

以下是本办法的实施:

## C++

```cpp
// CPP Program to check if three straight
// line are concurrent or not
#include <bits/stdc++.h>
using namespace std;

// Return true if three line are concurrent,
// else false.
bool checkConcurrent(int a1, int b1, int c1,
                     int a2, int b2, int c2,
                     int a3, int b3, int c3)
{
    return (a3 * (b1 * c2 - b2 * c1) +
            b3 * (c1 * a2 - c2 * a1) + 
            c3 * (a1 * b2 - a2 * b1) == 0);
}

// Driven Program
int main()
{
    int a1 = 2, b1 = -3, c1 = 5;
    int a2 = 3, b2 = 4, c2 = -7;
    int a3 = 9, b3 = -5, c3 = 8;

    (checkConcurrent(a1, b1, c1, a2, b2, c2,
     a3, b3, c3) ? (cout << "Yes") : (cout << "No"));
    return 0;
}
```

## Java

```java
// Java Program to check if three straight
// line are concurrent or no
import java.io.*;

class GFG {

    // Return true if three line are concurrent,
    // else false.
    static boolean checkConcurrent(int a1, int b1,
                   int c1, int a2, int b2, int c2,
                           int a3, int b3, int c3)
    {
        return (a3 * (b1 * c2 - b2 * c1) +
                b3 * (c1 * a2 - c2 * a1) +
                c3 * (a1 * b2 - a2 * b1) == 0);
    }

    // Driven Program
    public static void main (String[] args)
    {
        int a1 = 2, b1 = -3, c1 = 5;
        int a2 = 3, b2 = 4, c2 = -7;
        int a3 = 9, b3 = -5, c3 = 8;

        if(checkConcurrent(a1, b1, c1, a2, b2,
                               c2, a3, b3, c3))
            System.out.println( "Yes");
        else
            System.out.println( "No");
    }
}

// This code is contributed by anuj_67.
```

## Python 3

```python
# Python3 Program to check if three straight
# line are concurrent or not

# Return true if three line are concurrent,
# else false.
def checkConcurrent(a1, b1, c1, a2, b2, c2,
                                 a3, b3, c3):

    return (a3 * (b1 * c2 - b2 * c1) +
            b3 * (c1 * a2 - c2 * a1) +
            c3 * (a1 * b2 - a2 * b1) == 0)

# Driven Program
a1 = 2
b1 = -3
c1 = 5
a2 = 3
b2 = 4
c2 = -7
a3 = 9
b3 = -5
c3 = 8

if(checkConcurrent(a1, b1, c1, a2, b2, c2,
                               a3, b3, c3)):
    print("Yes")
else:
    print("No")

# This code is contributed by Smitha
```

## C#

```csharp
// C# Program to check if three straight
// line are concurrent or no
using System;

class GFG {

    // Return true if three line are concurrent,
    // else false.
    static bool checkConcurrent(int a1, int b1,
                int c1, int a2, int b2, int c2,
                        int a3, int b3, int c3)
    {
        return (a3 * (b1 * c2 - b2 * c1) +
                b3 * (c1 * a2 - c2 * a1) +
                c3 * (a1 * b2 - a2 * b1) == 0);
    }

    // Driven Program
    public static void Main ()
    {
        int a1 = 2, b1 = -3, c1 = 5;
        int a2 = 3, b2 = 4, c2 = -7;
        int a3 = 9, b3 = -5, c3 = 8;

        if(checkConcurrent(a1, b1, c1, a2, b2,
                            c2, a3, b3, c3))
            Console.WriteLine( "Yes");
        else
            Console.WriteLine( "No");
    }
}

// This code is contributed by anuj_67.
```

## PHP

```php
<?php
// PHP Program to check if three straight
// line are concurrent or not

// Return true if three line are
// concurrent, else false.
function checkConcurrent($a1, $b1, $c1,
                         $a2, $b2, $c2,
                         $a3, $b3, $c3)
{
    return ($a3 * ($b1 * $c2 - $b2 * $c1) +
            $b3 * ($c1 * $a2 - $c2 * $a1) +
            $c3 * ($a1 * $b2 - $a2 * $b1) == 0);
}  

    // Driver Code
    $a1 = 2; $b1 = -3; $c1 = 5;
    $a2 = 3; $b2 = 4; $c2 = -7;
    $a3 = 9; $b3 = -5; $c3 = 8;

    if(checkConcurrent($a1, $b1, $c1, $a2, $b2,
                           $c2, $a3, $b3, $c3))
        echo "Yes";
    else
        echo "No";

// This code is contributed by anuj_67.
?>
```

## JavaScript

```javascript
<script>

// Javascript Program to check if three straight
// line are concurrent or not

// Return true if three line are concurrent,
// else false.
function checkConcurrent( a1,  b1,  c1,
                       a2,  b2,  c2,
                       a3,  b3,  c3)
{
    return (a3 * (b1 * c2 - b2 * c1) +
            b3 * (c1 * a2 - c2 * a1) + 
            c3 * (a1 * b2 - a2 * b1) == 0);
}

// Driven Program
a1 = 2, b1 = -3, c1 = 5;
a2 = 3, b2 = 4, c2 = -7;
a3 = 9, b3 = -5, c3 = 8;
(checkConcurrent(a1, b1, c1, a2, b2, c2,
 a3, b3, c3) ? (document.write( "Yes")) : (document.write( "No")));

</script>
```

**Output:**

```
Yes
```