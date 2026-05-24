# 前 n 个自然数的立方和程序

> 原文：[https://www.geeksforgeeks.org/program-cube-sum-first-n-natural-numbers/](https://www.geeksforgeeks.org/program-cube-sum-first-n-natural-numbers/)

打印系列 $1^3+2^3+3^3+4^3+……+ n^3$ 直到第 n 项。

**举例：**

```
Input : n = 5
Output : 225
1^3 + 2^3 + 3^3 + 4^3 + 5^3 = 225

Input : n = 7
Output : 784
1^3 + 2^3 + 3^3 + 4^3 + 5^3 + 
6^3 + 7^3 = 784
```

一个**简单的解决方法**就是一个个添加项。

## C++

```cpp
// Simple C++ program to find sum of series
// with cubes of first n natural numbers
#include <iostream>
using namespace std;

/* Returns the sum of series */
int sumOfSeries(int n)
{
    int sum = 0;
    for (int x = 1; x <= n; x++)
        sum += x * x * x;
    return sum;
}

// Driver Function
int main()
{
    int n = 5;
    cout << sumOfSeries(n);
    return 0;
}
```

## Java

```java
// Simple Java program to find sum of series
// with cubes of first n natural numbers

import java.util.*;
import java.lang.*;
class GFG {

    /* Returns the sum of series */
    public static int sumOfSeries(int n)
    {
        int sum = 0;
        for (int x = 1; x <= n; x++)
            sum += x * x * x;
        return sum;
    }

    // Driver Function
    public static void main(String[] args)
    {
        int n = 5;
        System.out.println(sumOfSeries(n));
    }
}

// Code Contributed by Mohit Gupta_OMG <(0_o)>
```

## Python 3

```python
# Simple Python program to find sum of series
# with cubes of first n natural numbers

# Returns the sum of series
def sumOfSeries(n):
    sum = 0
    for i in range(1, n + 1):
        sum += i * i*i

    return sum

# Driver Function
n = 5
print(sumOfSeries(n))

# Code Contributed by Mohit Gupta_OMG <(0_o)>
```

## C#

```csharp
// Simple C# program to find sum of series
// with cubes of first n natural numbers
using System;

class GFG {
    /* Returns the sum of series */
    static int sumOfSeries(int n)
    {
        int sum = 0;
        for (int x = 1; x <= n; x++)
            sum += x * x * x;
        return sum;
    }

    // Driver Function
    public static void Main()
    {
        int n = 5;
        Console.Write(sumOfSeries(n));
    }
}
// This code is contributed by
// Smitha Dinesh Semwal
```

## PHP

```php
<?php
// Simple PHP program to find sum of series
// with cubes of first n natural numbers

// Returns the sum of series
function sumOfSeries( $n)
{
    $sum = 0;
    for ($x = 1; $x <= $n; $x++)
        $sum += $x * $x * $x;
    return $sum;
}

// Driver code
$n = 5;
echo sumOfSeries($n);

// This Code is contributed by vt_m.
?>
```

## JavaScript

```javascript
<script>

//  Simple javascript program to find sum of series
// with cubes of first n natural numbers

/* Returns the sum of series */
function sumOfSeries( n)
{
    let sum = 0;
    for (let x = 1; x <= n; x++)
        sum += x * x * x;
    return sum;
}

// Driven Program

    let n = 5;
     document.write(sumOfSeries(n));

// This code contributed by aashish1995

</script>
```

**输出：**

```
225
```

时间复杂度：`O(n)`

一个**有效的解决方案**是使用直接的数学公式 `(n * (n + 1) / 2)^2`

```
For n = 5 sum by formula is
       (5*(5 + 1 ) / 2)) ^ 2
          = (5*6/2) ^ 2
          = (15) ^ 2
          = 225

For n = 7, sum by formula is
       (7*(7 + 1 ) / 2)) ^ 2
          = (7*8/2) ^ 2
          = (28) ^ 2
          = 784
```

## C++

```cpp
// A formula based C++ program to find sum
// of series with cubes of first n natural
// numbers
#include <iostream>
using namespace std;

int sumOfSeries(int n)
{
    int x = (n * (n + 1) / 2);
    return x * x;
}

// Driver Function
int main()
{
    int n = 5;
    cout << sumOfSeries(n);
    return 0;
}
```

## Java

```java
// A formula based Java program to find sum
// of series with cubes of first n natural
// numbers

import java.util.*;
import java.lang.*;
class GFG {
    /* Returns the sum of series */
    public static int sumOfSeries(int n)
    {
        int x = (n * (n + 1) / 2);

        return x * x;
    }

    // Driver Function
    public static void main(String[] args)
    {
        int n = 5;
        System.out.println(sumOfSeries(n));
    }
}

// Code Contributed by Mohit Gupta_OMG <(0_o)>
```

## Python 3

```python
# A formula based Python program to find sum
# of series with cubes of first n natural
# numbers

# Returns the sum of series
def sumOfSeries(n):
    x = (n * (n + 1)  / 2)
    return (int)(x * x)

# Driver Function
n = 5
print(sumOfSeries(n))

# Code Contributed by Mohit Gupta_OMG <(0_o)>
```

## C#

```csharp
// A formula based C# program to
// find sum of series with cubes
// of first n natural numbers
using System;

class GFG {

    // Returns the sum of series
    public static int sumOfSeries(int n)
    {
        int x = (n * (n + 1) / 2);

        return x * x;
    }

    // Driver Function
    public static void Main()
    {
        int n = 5;

        Console.Write(sumOfSeries(n));
    }
}

// Code Contributed by nitin mittal.
```

## PHP

```php
<?php
// A formula based PHP program to find sum
// of series with cubes of first n natural
// numbers

function sumOfSeries($n)
{
    $x = ($n * ($n + 1) / 2);
    return $x * $x;
}

// Driver Function
$n = 5;
echo sumOfSeries($n);

// This code is contributed by vt_m.
?>
```

## JavaScript

```javascript
<script>

// Simple javascript program to find sum of series
// with cubes of first n natural numbers

/* Returns the sum of series */
function sumOfSeries( n)
{
    x = (n * (n + 1) / 2)
    return (x * x)
}

// Driven Program

    let n = 5;
    document.write(sumOfSeries(n));

// This code is contributed by sravan kumar

</script>
```

**输出：**

```
225
```

时间复杂度：`O(1)`

**这个公式是如何工作的？**
我们可以用数学归纳法证明这个公式。我们可以很容易地看到，这个公式适用于 `n = 1` 和 `n = 2`。假设 `n = k-1` 是真的。

```
Let the formula be true for n = k-1.
Sum of first (k-1) natural numbers = 
            [((k - 1) * k)/2]^2

Sum of first k natural numbers = 
          = Sum of (k-1) numbers + k^3
          = [((k - 1) * k)/2]^2 + k^3
          = [k^2(k^2 - 2k + 1) + 4k^3]/4
          = [k^4 + 2k^3 + k^2]/4
          = k^2(k^2 + 2k + 1)/4
          = [k*(k+1)/2]^2
```

**以上程序导致溢出，即使结果没有超出整数限制。**像[之前的帖子](https://www.geeksforgeeks.org/program-find-sum-first-n-natural-numbers/)一样，我们可以通过先做除法在一定程度上避免溢出。

## C++

```cpp
// Efficient CPP program to find sum of cubes
// of first n natural numbers that avoids
// overflow if result is going to be withing
// limits.
#include <iostream>
using namespace std;

// Returns sum of first n natural
// numbers
int sumOfSeries(int n)
{
    int x;
    if (n % 2 == 0)
        x = (n / 2) * (n + 1);
    else
        x = ((n + 1) / 2) * n;
    return x * x;
}

// Driver code
int main()
{
    int n = 5;
    cout << sumOfSeries(n);
    return 0;
}
```

## Java

```java
// Efficient Java program to find sum of cubes
// of first n natural numbers that avoids
// overflow if result is going to be withing
// limits.
import java.util.*;
import java.lang.*;
class GFG {
    /* Returns the sum of series */
    public static int sumOfSeries(int n)
    {
        int x;
        if (n % 2 == 0)
            x = (n / 2) * (n + 1);
        else
            x = ((n + 1) / 2) * n;
        return x * x;
    }

    // Driver Function
    public static void main(String[] args)
    {
        int n = 5;
        System.out.println(sumOfSeries(n));
    }
}
// Code Contributed by Mohit Gupta_OMG <(0_o)>
```

## Python 3

```python
# Efficient Python program to find sum of cubes
# of first n natural numbers that avoids
# overflow if result is going to be withing
# limits.

# Returns the sum of series
def sumOfSeries(n):
    x = 0
    if n % 2 == 0 :
        x = (n / 2) * (n + 1)
    else:
        x = ((n + 1) / 2) * n

    return (int)(x * x)

# Driver Function
n = 5
print(sumOfSeries(n))

# Code Contributed by Mohit Gupta_OMG <(0_o)>
```

# C#

```csharp
// Efficient C# program to find sum of
// cubes of first n natural numbers
// that avoids overflow if result is
// going to be withing limits.
using System;

class GFG {

    /* Returns the sum of series */
    public static int sumOfSeries(int n)
    {
        int x;
        if (n % 2 == 0)
            x = (n / 2) * (n + 1);
        else
            x = ((n + 1) / 2) * n;
        return x * x;
    }

    // Driver code
    static public void Main ()
    {
        int n = 5;
        Console.WriteLine(sumOfSeries(n));
    }
}

// This code is contributed by Ajit.
```

# 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```php
<?php
// Efficient PHP program to
// find sum of cubes of first 
// n natural numbers that avoids
// overflow if result is going
// to be with in limits.

// Returns sum of first n
// natural numbers
function sumOfSeries($n)
{
    $x;
    if ($n % 2 == 0)
        $x = ($n / 2) * ($n + 1);
    else
        $x = (($n + 1) / 2) * $n;
    return $x * $x;
}

// Driver code
$n = 5;
echo sumOfSeries($n);

// This code is contributed by vt_m.
?>
```

# java 描述语言

```javascript
<script>

// Simple javascript program to find sum of series
// with cubes of first n natural numbers

/* Returns the sum of series */
function sumOfSeries( n)
{
  x=0
    if (n % 2 == 0)
        x = (n / 2) * (n + 1)
    else
        x = ((n + 1) / 2) * n

    return (x * x)
}

// Driven Program

    let n = 5;
    document.write(sumOfSeries(n));

// This code contributed by sravan

</script>
```

### 输出:

本文由 **R_Raj** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用`contribute.geeksforgeeks.org`写一篇文章或者把你的文章邮寄到`contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。