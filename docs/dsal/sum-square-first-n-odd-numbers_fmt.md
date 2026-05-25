# 前 n 个奇数的平方和

> 原文: [https://www.geeksforgeeks.org/sum-square-first-n-odd-numbers/](https://www.geeksforgeeks.org/sum-square-first-n-odd-numbers/)

给定一个数 `n`，求前 `n` 个奇数自然数的平方和。

**例:**

```
Input : 3
Output : 35 
1^2 + 3^2 + 5^2 = 35

Input : 8
Output : 680
1^2 + 3^2 + 5^2 + 7^2 + 9^2 + 11^2 + 13^2 + 15^2 
```

一个简单的解法就是遍历 `n` 个奇数，求平方和。

下面是该方法的实现。

## C++

```cpp
// Simple C++ method to find sum of square of
// first n odd numbers.
#include <iostream>
using namespace std;

int squareSum(int n)
{
    int sum = 0;
    for (int i = 1; i <=  n; i++)
        sum += (2*i - 1) * (2*i - 1);
    return sum;
}

int main()
{
    cout << squareSum(8);
    return 0;
}
```

## Java

```java
// Simple Java method to
// find sum of square of
// first n odd numbers.

import java.io.*;

class GFG {

    static int squareSum(int n)
    {
        int sum = 0;
        for (int i = 1; i <=  n; i++)
            sum += (2*i - 1) * (2*i - 1);
        return sum;
    }

    //Driver Code
    public static void main(String args[])
    {   
        System.out.println(squareSum(8));
    }
}

// This code is contributed by
// Nikita tiwari.
```

## Python 3

```python
# Simple Python method
# to find sum of square
# of first n odd numbers.
def squareSum(n):

    sm = 0
    for i in range(1, n + 1):
        sm += (2 * i - 1) * (2 * i - 1)

    return sm

# Driver Code
n=8
print(squareSum(n))

# This code is contributed by Ansu Kumari
```

## C#

```csharp
// Simple C# method to find
// sum of square of first
// n odd numbers.
using System;

class GFG {

    static int squareSum(int n)
    {
        int sum = 0;
        for (int i = 1; i <= n; i++)
            sum += (2*i - 1) * (2*i - 1);
        return sum;
    }

    // Driver Code
    public static void Main()
    {
        Console.Write(squareSum(8));
    }
}

// This code is contributed by
// vt_m.
```

## PHP

```php
<?php
// Simple PHP method to find sum
// of square of first n odd numbers.

function squareSum( $n)
{
    $sum = 0;
    for ($i = 1; $i <= $n; $i++)
        $sum += (2*$i - 1) * (2*$i - 1);
    return $sum;
}

    echo squareSum(8);

// This code is contributed by Vt_m.
?>
```

## JavaScript

```javascript
<script>

// Simple Javascript method to find
// sum of square of first n odd numbers.
function squareSum(n)
{
    let sum = 0;
    for(let i = 1; i <=  n; i++)
        sum += (2 * i - 1) * (2 * i - 1);

    return sum;
}

// Driver code
document.write(squareSum(8));

// This code is contributed by souravmahato348

</script>
```

**输出:**

```
680
```

一个有效的解决方案是应用下面的公式。

```
sum = n * (4n^2 - 1) / 3

How does it work? 
Please refer sum of squares of even and odd
numbers for proof.
```

## C++

```cpp
// Efficient C++ method to find sum of
// square of first n odd numbers.
#include <iostream>
using namespace std;

int squareSum(int n)
{
    return n*(4*n*n - 1)/3;
}

int main()
{
    cout << squareSum(8);
    return 0;
}
```

## Java

```java
// Efficient Java method
// to find sum of
// square of first n odd numbers.

import java.io.*;

class GFG {

    static int squareSum(int n)
    {
        return n*(4*n*n - 1)/3;
    }

    public static void main(String args[])
    {
        System.out.println(squareSum(8));
    }
}

// This code is contributed by
// Nikita tiwari.
```

## Python 3

```python
# Python3 code to find sum
# of square of first n odd numbers

def squareSum( n ):

    return int(n * ( 4 * n * n - 1) / 3)

# driver code
ans = squareSum(8)
print (ans)

# This code is contributed by Saloni Gupta
```

## C#

```csharp
// Efficient C# method to
// find sum of square of
// first n odd numbers.
using System;

class GFG {

    static int squareSum(int n)
    {
        return n * (4 * n * n - 1)/3;
    }

    // driver code   
    public static void Main()
    {
        Console.Write(squareSum(8));
    }
}

// This code is contributed by
// Vt_m.
```

## PHP

```php
<?php
// Efficient PHP method to find sum of
// square of first n odd numbers.

function squareSum($n)
{
    return $n * (4 * $n * $n - 1) / 3;
}

    echo squareSum(8);

// This code is contributed by Vt_m.
?>
```

## JavaScript

```javascript
<script>
// Efficient Javascript method to find
// sum of square of first n odd numbers.
function squareSum(n)
{
    return n * (4 * n * n - 1) / 3;
}

// Driver code
document.write(squareSum(8));

// This code is contributed by sravan kumar
</script>
```

**输出:**

```
680
```