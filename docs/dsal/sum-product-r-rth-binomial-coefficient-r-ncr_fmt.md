# r 与 rth 二项式系数(r * nCr)乘积之和

> 原文: [https://www.geeksforgeeks.org/sum-product-r-rth-binomial-coefficient-r-ncr/](https://www.geeksforgeeks.org/sum-product-r-rth-binomial-coefficient-r-ncr/)

给定正整数 `n`。任务是求 `r` 和 `r` 的 `th` 二项式系数乘积之和。换句话说就是找：`σ(r * nCr)`，其中 `0 <= r <= n`。

**例:**

```
Input : n = 2
Output : 4
0.2C0 + 1.2C1 + 2.2C2
= 0*2 + 1*2 + 2*1
= 4

Input : n = 5
Output : 80
```

**方法 1(蛮力):** 思路是从 `0` 到 `n` 迭代一个循环 `i`，求 `i * nCi` 加和变量。
以下是该方法的实现:

## C++

```cpp
// CPP Program to find sum of product of r and
// rth Binomial Coefficient i.e summation r * nCr
#include <bits/stdc++.h>
using namespace std;
#define MAX 100

// Return the first n term of binomial coefficient.
void binomialCoeff(int n, int C[])
{
    C[0] = 1; // nC0 is 1

    for (int i = 1; i <= n; i++) {

        // Compute next row of pascal triangle
        // using the previous row
        for (int j = min(i, n); j > 0; j--)
            C[j] = C[j] + C[j - 1];
    }
}

// Return summation of r * nCr
int summation(int n)
{
    int C[MAX];
    memset(C, 0, sizeof(C));

    // finding the first n term of binomial
    // coefficient
    binomialCoeff(n, C);

    // Iterate a loop to find the sum.
    int sum = 0;
    for (int i = 0; i <= n; i++)
        sum += (i * C[i]);   

    return sum;
}

// Driven Program
int main()
{
    int n = 2;
    cout << summation(n) << endl;
    return 0;
}
```

## Java

```java
// Java Program to find sum
// of product of r and rth
// Binomial Coefficient i.e
// summation r * nCr
class GFG
{
static int MAX = 100;

// Return the first n term
// of binomial coefficient.
static void binomialCoeff(int n,
                          int C[])
{
    C[0] = 1; // nC0 is 1

    for (int i = 1; i <= n; i++)
    {

        // Compute next row of
        // pascal triangle using
        // the previous row
        for (int j = Math.min(i, n); j > 0; j--)
            C[j] = C[j] + C[j - 1];
    }
}

// Return summation
// of r * nCr
static int summation(int n)
{
    int C[] = new int[MAX];

    for(int i = 0; i < MAX; i++)
    C[i] = 0;

    // finding the first n term 
    // of binomial coefficient
    binomialCoeff(n, C);

    // Iterate a loop
    // to find the sum.
    int sum = 0;
    for (int i = 0; i <= n; i++)
        sum += (i * C[i]);

    return sum;
}

// Driver Code
public static void main(String args[])
{
    int n = 2;
    System.out.println( summation(n));
}
}

// This code is contributed by Arnab Kundu
```

## Python 3

```python
# Python 3 Program to find sum of product
# of r and rth Binomial Coefficient i.e
# summation r * nCr
MAX = 100

# Return the first n term of
# binomial coefficient.
def binomialCoeff(n, C):

    C[0] = 1 # nC0 is 1

    for i in range(1, n + 1):

        # Compute next row of pascal triangle
        # using the previous row
        for j in range(min(i, n), -1, -1):
            C[j] = C[j] + C[j - 1]

# Return summation of r * nCr
def summation( n):

    C = [0] * MAX

    # finding the first n term of
    # binomial coefficient
    binomialCoeff(n, C)

    # Iterate a loop to find the sum.
    sum = 0
    for i in range(n + 1):
        sum += (i * C[i])

    return sum

# Driver Code
if __name__ == "__main__":

    n = 2
    print(summation(n))

# This code is contributed by ita_c
```

## C#

```csharp
// C# Program to find sum
// of product of r and rth
// Binomial Coefficient i.e
// summation r * nCr
using System;

class GFG
{
static int MAX = 100;

// Return the first n term
// of binomial coefficient.
static void binomialCoeff(int n,
                          int []C)
{
    C[0] = 1; // nC0 is 1

    for (int i = 1; i <= n; i++)
    {

        // Compute next row of
        // pascal triangle using
        // the previous row
        for (int j = Math.Min(i, n);
                 j > 0; j--)
            C[j] = C[j] + C[j - 1];
    }
}

// Return summation
// of r * nCr
static int summation(int n)
{
    int []C = new int[MAX];

    for(int i = 0; i < MAX; i++)
    C[i] = 0;

    // finding the first n term
    // of binomial coefficient
    binomialCoeff(n, C);

    // Iterate a loop
    // to find the sum.
    int sum = 0;
    for (int i = 0; i <= n; i++)
        sum += (i * C[i]);

    return sum;
}

// Driver Code
public static void Main()
{
    int n = 2;
    Console.Write( summation(n));
}
}

// This code is contributed
// by shiv_bhakt
```

## PHP

```php
<?php
// PHP Program to find sum of product
// of r and rth Binomial Coefficient
// i.e summation r * nCr
$MAX = 100;

// Return the first n term of
// binomial coefficient.
function binomialCoeff($n, &$C)
{
    $C[0] = 1; // nC0 is 1

    for ($i = 1; $i <= $n; $i++)
    {

        // Compute next row of pascal triangle
        // using the previous row
        for ($j = min($i, $n); $j > 0; $j--)
            $C[$j] = $C[$j] + $C[$j - 1];
    }
}

// Return summation of r * nCr
function summation($n)
{
    global $MAX;
    $C = array_fill(0, $MAX, 0);

    // finding the first n term of
    // binomial coefficient
    binomialCoeff($n, $C);

    // Iterate a loop to find the sum.
    $sum = 0;
    for ($i = 0; $i <= $n; $i++)
        $sum += ($i * $C[$i]);

    return $sum;
}

// Driver Code
$n = 2;
echo summation($n);

// This code is contributed by mits
?>
```

## JavaScript

```javascript
<script>

    // Javascript Program to find sum of product of r and
    // rth Binomial Coefficient i.e summation r * nCr
    MAX = 100

    // Return the first n term of binomial coefficient.
    function binomialCoeff(n, C) {
      C[0] = 1; // nC0 is 1

      for (var i = 1; i <= n; i++) {

        // Compute next row of pascal triangle
        // using the previous row
        for (var j = Math.min(i, n); j > 0; j--)
          C[j] = C[j] + C[j - 1];
      }
    }

    // Return summation of r * nCr
    function summation(n) {
      C = Array(MAX).fill(0);

      // finding the first n term of binomial
      // coefficient
      binomialCoeff(n, C);

      // Iterate a loop to find the sum.
      var sum = 0;
      for (var i = 0; i <= n; i++)
        sum += (i * C[i]);

      return sum;
    }

    // Driven Program
    var n = 2;
    document.write(summation(n));

    // This code is contributed by noob2000.
  </script>
```

**Output:**

```
4
```

**方法二(使用公式):**
数学上我们需要找到，
`σ(i * nCi)`，其中 `0 <= i <= n`
`=σ(iCi * nCi)`，(自 `nCi = i!/(i–1)! * 1!)* (n!/(n–i)! * i!`)
关于取消 `i!` 从分子和分母
`=σ(n!/(i–1)!*(n–i)!)`
`=σn * (n–1)!/(i–1)!*(n–i)!)`
(使用 `nCr` 的反向= `(n)!/ (r)!*(n–r)!`)
`= n * σn–1Cr–1`
`= n * 2n–1`(自 `σnCr = 2n`)
以下为本办法执行情况:

## C++

```cpp
// CPP Program to find sum of product of r and
// rth Binomial Coefficient i.e summation r * nCr
#include <bits/stdc++.h>
using namespace std;
#define MAX 100

// Return summation of r * nCr
int summation(int n)
{
    return n << (n - 1);
}

// Driven Program
int main()
{
    int n = 2;
    cout << summation(n) << endl;
    return 0;
}
```

## Java

```java
// Java Program to find sum of product of
// r and rth Binomial Coefficient i.e
// summation r * nCr
import java.io.*;

class GFG {

    static int MAX = 100;

    // Return summation of r * nCr
    static int summation(int n)
    {
        return n << (n - 1);
    }

    // Driven Program
    public static void main (String[] args)
    {
        int n = 2;
        System.out.println( summation(n));
    }
}

// This code is contributed by anuj_67.
```

## Python 3

```python
# Python3 Program to
# find sum of product
# of r and rth Binomial
# Coefficient i.e
# summation r * nCr

# Return summation
# of r * nCr
def summation( n):
    return n << (n - 1);

# Driver Code
n = 2;
print(summation(n));

# This code is contributed
# by mits
```

## C#

```
// C# Program to find sum of product of
// r and rth Binomial Coefficient i.e
// summation r * nCr
using System;

class GFG {

    //static int MAX = 100;

    // Return summation of r * nCr
    static int summation(int n)
    {
        return n << (n - 1);
    }

    // Driver Code
    public static void Main ()
    {
        int n = 2;
        Console.WriteLine( summation(n));
    }
}

// This code is contributed by anuj_67.
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```
<?php
// PHP Program to find sum
// of product of r and
// rth Binomial Coefficient
// i.e summation r * nCr

// Return summation of r * nCr
function summation( $n)
{
    return $n << ($n - 1);
}

// Driver Code
$n = 2;
echo summation($n) ;

// This code is contributed
// by shiv_bhakt
?>
```

## java 描述语言

```
<script>

// Javascript Program to find sum of product of r and
// rth Binomial Coefficient i.e summation r * nCr
var MAX=100

// Return summation of r * nCr
function summation(n)
{
    return n << (n - 1);
}

// Driven Program
var n = 2;
document.write(summation(n));

</script>
```

**Output:**

```

```