# 等差数列第 N 项程序

> 原文: [https://www.geeksforgeeks.org/program-n-th-term-arithmetic-progression-series/](https://www.geeksforgeeks.org/program-n-th-term-arithmetic-progression-series/)

给定等差数列的第一项(`a`)、公共差(`d`)和整数 `N`，任务是找到数列的第 `N`<sup>项。</sup>

**例：**

```
Input : a = 2 d = 1 N = 5
Output :
The 5th term of the series is : 6

Input : a = 5 d = 2 N = 10
Output :
The 10th term of the series is : 23
```

**进场：**

> 我们知道等差数列就像 = 2，5，8，11，14。…
> 在本系列中，2 是该系列的陈述性术语。
> 公差 = 5–2 = 3（系列中的公差）。
> 所以我们可以把系列写成：
> `t1 = a1`
> `t2 = a1 + (2-1) * d`
> `t3 = a1 + (3-1) * d`
> 。
> 。
> 。
> `tN = a1 + (N-1) * d`

为了在算术级数中找到第 `N`<sup>项，我们使用了简单的公式。</sup>

```
TN = a1 + (N-1) * d
```

## C++

```cpp
// CPP Program to find nth term of
// Arithmetic progression
#include <bits/stdc++.h>
using namespace std;

int Nth_of_AP(int a, int d, int N)
{
    // using formula to find the
    // Nth term t(n) = a(1) + (n-1)*d
    return (a + (N - 1) * d);

}

// Driver code
int main()
{
    // starting number
    int a = 2;

    // Common difference
    int d = 1;

    // N th term to be find
    int N = 5;

    // Display the output
    cout << "The "<< N
         <<"th term of the series is : "
         << Nth_of_AP(a,d,N);

    return 0;
}
```

## Java

```java
// Java program to find nth term
// of Arithmetic progression
import java.io.*;
import java.lang.*;

class GFG
{
    public static int Nth_of_AP(int a,
                                int d,
                                int N)
    {
        // using formula to find the Nth
        // term t(n) = a(1) + (n-1)*d
        return ( a + (N - 1) * d );
    }

    // Driver code
    public static void main(String[] args)
    {
        // starting number
        int a = 2;

        // Common difference
        int d = 1;

        // N th term to be find
        int N = 5;

        // Display the output
        System.out.print("The "+ N +
                         "th term of the series is : " +
                          Nth_of_AP(a, d, N));
    }
}
```

## Python 3

```python
# Python 3 Program to
# find nth term of
# Arithmetic progression

def Nth_of_AP(a, d, N) :

    # using formula to find the
    # Nth term t(n) = a(1) + (n-1)*d
    return (a + (N - 1) * d)

# Driver code
a = 2  # starting number
d = 1  # Common difference
N = 5  # N th term to be find

# Display the output
print( "The ", N ,"th term of the series is : ",
       Nth_of_AP(a, d, N))

# This code is contributed
# by Nikita Tiwari.
```

## C\#

```csharp
// C# program to find nth term
// of Arithmetic progression
using System;

class GFG
{
    public static int Nth_of_AP(int a,
                                int d,
                                int N)
    {

        // using formula to find the Nth
        // term t(n) = a(1) + (n-1)*d
        return ( a + (N - 1) * d );
    }

    // Driver code
    public static void Main()
    {
        // starting number
        int a = 2;

        // Common difference
        int d = 1;

        // N th term to be find
        int N = 5;

        // Display the output
        Console.WriteLine("The "+ N +
                          "th term of the series is : " +
                           Nth_of_AP(a, d, N));
    }
}

// This code is contributed by vt_m.
```

## PHP

```php
<?php
// PHP Program to find nth term of
// Arithmetic progression

function Nth_of_AP($a, $d, $N)
{
    // using formula to find the
    // Nth term t(n) = a(1) + (n-1)*d
    return ($a + ($N - 1) * $d);

}

// Driver code

// starting number
$a = 2;

// Common difference
$d = 1;

// N th term to be find
$N = 5;

// Display the output
echo("The " . $N . "th term of the series is : " .
                       Nth_of_AP($a, $d, $N));

// This code is contributed by Ajit.
?>
```

## JavaScript

```javascript
<script>

// JavaScript Program to find nth term of 
// Arithmetic progression

    function Nth_of_AP(a, d, N)
    { 
        // using formula to find the 
        // Nth term t(n) = a(1) + (n-1)*d
        return (a + (N - 1) * d);

    }

    // Driver code

    // starting number
    let a = 2; 

    // Common difference
    let d = 1; 

    // N th term to be find
    let N = 5; 

    // Display the output
    document.write("The "+ N + "th term of the series is : "
    + Nth_of_AP(a,d,N));

// This code is contributed by Mayank Tyagi

</script>
```

**输出：**

```
The 5th term of the series is : 6
```