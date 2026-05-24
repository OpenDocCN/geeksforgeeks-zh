# 几何级数第 N 项程序

> 原文: [https://www.geeksforgeeks.org/find-nth-term-geometric-progression-series/](https://www.geeksforgeeks.org/find-nth-term-geometric-progression-series/)

给定几何级数的第一项(`a`)、公比(`r`)和整数 `N`，任务是找到级数的第 `N`<sup>项</sup>。

**例:**

```
Input : a = 2, r = 2, N = 4
Output :
The 4th term of the series is : 16

Input : a = 2, r = 3, N = 5
Output :
The 5th term of the series is : 162
```

**进场:**

> 我们知道几何级数就像 = 2, 4, 8, 16, 32。…
> 在本系列中，2 是该系列的陈述性术语。
> 公比 = 4 / 2 = 2 (系列中的公比)。
> 所以我们可以把这个系列写成:
> `t1 = a1`
> `t2 = a1 * r^(2-1)`
> `t3 = a1 * r^(3-1)`
> `t4 = a1 * r^(4-1)`
> 。
> 。
> 。
> `tN = a1 * r^(N-1)`

为了在几何级数中找到第 `N`<sup>项，我们使用了简单的公式。</sup>

```
T_N = a1 * r^(N-1)
```

## C++

```cpp
// CPP Program to find nth term of
// geometric progression
#include <bits/stdc++.h>

using namespace std;

int Nth_of_GP(int a, int r, int N)
{
    // using formula to find
    // the Nth term
    // TN = a1 * r(N-1)
    return( a * (int)(pow(r, N - 1)) );

}

// Driver code
int main()
{
    // starting number
    int a = 2;

    // Common ratio
    int r = 3;

    // N th term to be find
    int N = 5;

    // Display the output
    cout << "The "<< N <<"th term of the series is : "
        << Nth_of_GP(a, r, N);

    return 0;
}
```

## Java

```java
// java program to find nth term
// of geometric progression
import java.io.*;
import java.lang.*;

class GFG
{
    public static int Nth_of_GP(int a,
                                int r,
                                int N)
    {
        // using formula to find the Nth
        // term TN = a1 * r(N-1)
        return ( a * (int)(Math.pow(r, N - 1)) );
    }

    // Driver code
    public static void main(String[] args)
    {
        // starting number
        int a = 2;

        // Common ratio
        int r = 3;

        // N th term to be find
        int N = 5;

        // Display the output
        System.out.print("The "+ N + "th term of the" +
                " series is : " + Nth_of_GP(a, r, N));
    }
}
```

## Python 3

```python
# Python3 Program to find nth
# term of geometric progression
import math

def Nth_of_GP(a, r, N):

    # Using formula to find the Nth
    # term TN = a1 * r(N-1)
    return( a * (int)(math.pow(r, N - 1)) )

# Driver code
a = 2 # Starting number
r = 3 # Common ratio
N = 5 # N th term to be find

print("The", N, "th term of the series is :",
                    Nth_of_GP(a, r, N))

# This code is contributed by Smitha Dinesh Semwal
```

## C\#

```csharp
// C# program to find nth term
// of geometric progression
using System;

class GFG
{

    public static int Nth_of_GP(int a,
                                int r,
                                int N)
    {

        // using formula to find the Nth
        // term TN = a1 * r(N-1)
        return ( a * (int)(Math.Pow(r, N - 1)) );
    }

    // Driver code
    public static void Main()
    {
        // starting number
        int a = 2;

        // Common ratio
        int r = 3;

        // N th term to be find
        int N = 5;

        // Display the output
        Console.Write("The "+ N + "th term of the" +
            " series is : " + Nth_of_GP(a, r, N));
    }
}

// This code is contributed by vt_m
```

## PHP

```php
<?php
// PHP Program to find nth term of
// geometric progression

function Nth_of_GP($a, $r, $N)
{
    // using formula to find
    // the Nth term TN = a1 * r(N-1)
    return( $a * (int)(pow($r, $N - 1)) );

}

// Driver code

// starting number
$a = 2;

// Common ratio
$r = 3;

// N th term to be find
$N = 5;

// Display the output
echo("The " . $N . "th term of the series is : "
                    . Nth_of_GP($a, $r, $N));

// This code is contributed by Ajit.
?>
```

## JavaScript

```javascript
<script>

// JavaScript Program to find nth term of 
// geometric progression 

function Nth_of_GP(a, r, N) 
{ 
    // using formula to find 
    // the Nth term 
    // TN = a1 * r(N-1) 
    return( a * Math.floor(Math.pow(r, N - 1)) ); 

} 

// Driver code 

    // starting number 
    let a = 2; 

    // Common ratio 
    let r = 3; 

    // N th term to be find 
    let N = 5; 

    // Display the output 
    document.write("The "+ N +"th term of the series is : "
        + Nth_of_GP(a, r, N)); 

// This code is contributed by Surbhi Tyagi

</script>
```

**输出:**

```
The 5th term of the series is : 162
```