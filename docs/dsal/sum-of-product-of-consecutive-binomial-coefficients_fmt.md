# 连续二项式系数乘积之和

> 原文:[https://www . geesforgeks . org/连续二项式系数乘积之和/](https://www.geeksforgeeks.org/sum-of-product-of-consecutive-binomial-coefficients/)

给定正整数 `n`。任务是求连续二项式系数的乘积之和即
`nC0*nC1 + nC1*nC2 + ….. + nCn-1*nCn`

## 示例

```
Input : n = 3
Output : 15
3C0*3C1 + 3C1*3C2 +3C2*3C3
= 1*3 + 3*3 + 3*1
= 3 + 9 + 3
= 15

Input : n = 4
Output : 56
```

## 方法一

思路是找出第 `n` 项之前的所有二项式系数，求连续系数乘积的和。

下面是该方法的实现:

### C++

```cpp
// CPP Program to find sum of product of
// consecutive Binomial Coefficient.
#include <bits/stdc++.h>
using namespace std;
#define MAX 100

// Find the binomial coefficient upto nth term
void binomialCoeff(int C[], int n)
{
    C[0] = 1; // nC0 is 1

    for (int i = 1; i <= n; i++) {

        // Compute next row of pascal triangle using
        // the previous row
        for (int j = min(i, n); j > 0; j--)
            C[j] = C[j] + C[j - 1];
    }
}

// Return the sum of the product of
// consecutive binomial coefficient.
int sumOfproduct(int n)
{
    int sum = 0;
    int C[MAX] = { 0 };

    binomialCoeff(C, n);

    // finding the sum of product of
    // consecutive coefficient.
    for (int i = 0; i <= n; i++)
        sum += C[i] * C[i + 1];   

    return sum;
}

// Driven Program
int main()
{
    int n = 3;
    cout << sumOfproduct(n) << endl;
    return 0;
}
```

### Java

```java
// Java Program to find sum of product of
// consecutive Binomial Coefficient.

import java.io.*;

class GFG {

static int  MAX = 100;

// Find the binomial coefficient upto nth term
static void binomialCoeff(int C[], int n)
{
    C[0] = 1; // nC0 is 1

    for (int i = 1; i <= n; i++) {

        // Compute next row of pascal triangle using
        // the previous row
        for (int j = Math.min(i, n); j > 0; j--)
            C[j] = C[j] + C[j - 1];
    }
}

// Return the sum of the product of
// consecutive binomial coefficient.
static int sumOfproduct(int n)
{
    int sum = 0;
    int C[] = new int[MAX];

    binomialCoeff(C, n);

    // finding the sum of product of
    // consecutive coefficient.
    for (int i = 0; i <= n; i++)
        sum += C[i] * C[i + 1];

    return sum;
}

// Driven Program

    public static void main (String[] args) {
    int n = 3;
    System.out.println( sumOfproduct(n));
    }
}

// This code is contributed by inder_verma..
```

### Python 3

```python
# Python3 Program to find sum of product
# of consecutive Binomial Coefficient.
MAX = 100;

# Find the binomial coefficient upto
# nth term
def binomialCoeff(C, n):

    C[0] = 1; # nC0 is 1

    for i in range(1, n + 1):

        # Compute next row of
        # pascal triangle using
        # the previous row
        for j in range(min(i, n), 0, -1):
            C[j] = C[j] + C[j - 1];

    return C;

# Return the sum of the product of
# consecutive binomial coefficient.
def sumOfproduct(n):

    sum = 0;
    C = [0] * MAX;

    C = binomialCoeff(C, n);

    # finding the sum of
    # product of consecutive
    # coefficient.
    for i in range(n + 1):
        sum += C[i] * C[i + 1];

    return sum;

# Driver Code
n = 3;
print(sumOfproduct(n));

# This code is contributed by mits
```

### C\#

```csharp
// C# Program to find sum of
// product of consecutive
// Binomial Coefficient.
using System;

class GFG
{
static int MAX = 100;

// Find the binomial coefficient
// upto nth term
static void binomialCoeff(int []C, int n)
{
    C[0] = 1; // nC0 is 1

    for (int i = 1; i <= n; i++)
    {

        // Compute next row of pascal
        // triangle using the previous row
        for (int j = Math.Min(i, n);
                 j > 0; j--)
            C[j] = C[j] + C[j - 1];
    }
}

// Return the sum of the product of
// consecutive binomial coefficient.
static int sumOfproduct(int n)
{
    int sum = 0;
    int []C = new int[MAX];

    binomialCoeff(C, n);

    // finding the sum of product of
    // consecutive coefficient.
    for (int i = 0; i <= n; i++)
        sum += C[i] * C[i + 1];

    return sum;
}

// Driven Code
public static void Main ()
{
    int n = 3;
    Console.WriteLine(sumOfproduct(n));
}
}

// This code is contributed by anuj_67
```

### PHP

```php
<?php
// PHP Program to find sum
// of product of consecutive
// Binomial Coefficient.
$MAX = 100;

// Find the binomial
// coefficient upto
// nth term
function binomialCoeff($C, $n)
{
    $C[0] = 1; // nC0 is 1

    for ($i = 1;
         $i <= $n; $i++)
    {

        // Compute next row of
        // pascal triangle using
        // the previous row
        for ($j = min($i, $n);
             $j > 0; $j--)
            $C[$j] = $C[$j] +
                     $C[$j - 1];
    }
    return $C;
}

// Return the sum of the
// product of consecutive
// binomial coefficient.
function sumOfproduct($n)
{
    global $MAX;
    $sum = 0;
    $C = array_fill(0, $MAX, 0);

    $C = binomialCoeff($C, $n);

    // finding the sum of
    // product of consecutive
    // coefficient.
    for ($i = 0; $i <= $n; $i++)
        $sum += $C[$i] * $C[$i + 1];

    return $sum;
}

// Driver Code
$n = 3;
echo sumOfproduct($n);

// This code is contributed by mits
?>
```

## java 描述语言

```javascript
<script>

// Javascript Program to find sum of product of
// consecutive Binomial Coefficient.
var MAX = 100;

// Find the binomial coefficient upto nth term
function binomialCoeff(C, n)
{
    C[0] = 1; // nC0 is 1

    for (var i = 1; i <= n; i++) {

        // Compute next row of pascal triangle using
        // the previous row
        for (var j = Math.min(i, n); j > 0; j--)
            C[j] = C[j] + C[j - 1];
    }
}

// Return the sum of the product of
// consecutive binomial coefficient.
function sumOfproduct(n)
{
    var sum = 0;
    var C = Array(MAX).fill(0);

    binomialCoeff(C, n);

    // finding the sum of product of
    // consecutive coefficient.
    for (var i = 0; i <= n; i++)
        sum += C[i] * C[i + 1];   

    return sum;
}

// Driven Program
var n = 3;
document.write( sumOfproduct(n));

</script>
```

## 输出

```

```

## 方法二:
我们知道，
`(1+x)^n = nC0 + nC1 * x + nC2 * x^2 + ... + nCn * x^n` ……(1)
`(1+1/x)^n = nC0 + nC1/x + nC2/x^2 + ... + nCn/x^n` ……(2)
将(1)和(2)相乘，我们得到
`(1+x)^(2n) / x^n = (nC0 + nC1 * x + nC2 * x^2 + ... + nCn * x^n) * (nC0 + nC1/x + nC2/x^2 + ... + nCn/x^n)`
`(2nC0 + 2nC1 * x + 2nC2 * x^2 + ... + 2nCn * x^n) / x^n = (nC0 + nC1 * x + nC2 * x^2 + ... + nCn * x^n) * (nC0 + nC1/x + nC2/x^2 + ... + nCn/x^n)`
现在，求出 LHS 的 `x` 系数，
观察分子中的 `r`th 展开项为 `2nCr * x^r`。
求 `x` 在 `(1+x)^(2n) / x^n` 中的系数，`r` 应该是 `n + 1`，因为 `x` 在分母中的幂会减少它。
那么，LHS 的 `x` 系数 = `2nC(n + 1)` 或 `2nC(n–1)`。
现在，求出 RHS 中的 `x` 系数，
乘法第一次展开的 `r` 项为 `nCr * x^r`。
乘法第二次展开的 `t` 项为 `nCt / x^t`。
所以乘法后的项为 `nCr * nCt * x^r / x^t`。
令 `r = t + 1`，我们得到，
`nC(t+1) * nCt * x`。
因此，RHS 中 `x` 的系数 = `nC0 * nC1 + nC1 * nC2 + ... + nC(n-1) * nCn`。
对比 LHS 和 RHS 的 `x` 系数，我们可以说，
`nC0 * nC1 + nC1 * nC2 + ... + nC(n-1) * nCn = 2nC(n-1)`。

下面是这种方法的实现:

## C++

```cpp
// CPP Program to find sum of product of
// consecutive Binomial Coefficient.
#include <bits/stdc++.h>
using namespace std;
#define MAX 100

// Find the binomial coefficient up to nth
// term
int binomialCoeff(int n, int k)
{
    int C[k + 1];
    memset(C, 0, sizeof(C));

    C[0] = 1; // nC0 is 1

    for (int i = 1; i <= n; i++) {

        // Compute next row of pascal triangle
        // using the previous row
        for (int j = min(i, k); j > 0; j--)
            C[j] = C[j] + C[j - 1];
    }
    return C[k];
}

// Return the sum of the product of
// consecutive binomial coefficient.
int sumOfproduct(int n)
{
    return binomialCoeff(2 * n, n - 1);
}

// Driven Program
int main()
{
    int n = 3;

    cout << sumOfproduct(n) << endl;
    return 0;
}
```

## Java 语言

```java
// Java Program to find sum of
// product of consecutive
// Binomial Coefficient.
import java.io.*;

class GFG
{
    static int MAX = 100;

    // Find the binomial coefficient
    // up to nth term
    static int binomialCoeff(int n,
                             int k)
    {
        int C[] = new int[k + 1];

        // memset(C, 0, sizeof(C));
        C[0] = 1; // nC0 is 1

        for (int i = 1; i <= n; i++)
        {

            // Compute next row of
            // pascal triangle
            // using the previous row
            for (int j = Math.min(i, k); j > 0; j--)
                C[j] = C[j] + C[j - 1];
    }

    return C[k];
}

// Return the sum of the
// product of consecutive
// binomial coefficient.
static int sumOfproduct(int n)
{
    return binomialCoeff(2 * n,
                         n - 1);
}

// Driver Code
public static void main (String[] args)
{
    int n = 3;
    System.out.println(sumOfproduct(n));
}
}

// This code is contributed
// by shiv_bhakt.
```

## Python 3

```python
# Python3 Program to find sum of product
# of consecutive Binomial Coefficient.
MAX = 100;

# Find the binomial coefficient
# up to nth term
def binomialCoeff(n, k):

    C = [0] * (k + 1);

    C[0] = 1; # nC0 is 1

    for i in range(1, n + 1):

        # Compute next row of pascal triangle
        # using the previous row
        for j in range(min(i, k), 0, -1):
            C[j] = C[j] + C[j - 1];
    return C[k];

# Return the sum of the product of
# consecutive binomial coefficient.
def sumOfproduct(n):
    return binomialCoeff(2 * n, n - 1);

# Driver Code
n = 3;
print(sumOfproduct(n));

# This code is contributed by mits
```

## C\#

```csharp
// C# Program to find sum of
// product of consecutive
// Binomial Coefficient.
using System;

class GFG
{

    // Find the binomial
    // coefficient up to
    // nth term
    static int binomialCoeff(int n,
                             int k)
    {
        int []C = new int[k + 1];

        // memset(C, 0, sizeof(C));
        C[0] = 1; // nC0 is 1

        for (int i = 1; i <= n; i++)
        {

            // Compute next row of
            // pascal triangle
            // using the previous row
            for (int j = Math.Min(i, k);
                             j > 0; j--)
                C[j] = C[j] + C[j - 1];
    }

    return C[k];
}

// Return the sum of the
// product of consecutive
// binomial coefficient.
static int sumOfproduct(int n)
{
    return binomialCoeff(2 * n,
                         n - 1);
}

// Driver Code
static public void Main ()
{
    int n = 3;
    Console.WriteLine(sumOfproduct(n));
}
}

// This code is contributed
// by @ajit.
```

## PHP

```php
<?php
// PHP Program to find sum of product of
// consecutive Binomial Coefficient.
$MAX = 100;

// Find the binomial coefficient
// up to nth term
function binomialCoeff($n, $k)
{
    $C = array_fill(0, ($k + 1), 0);

    $C[0] = 1; // nC0 is 1

    for ($i = 1; $i <= $n; $i++)
    {

        // Compute next row of pascal triangle
        // using the previous row
        for ($j = min($i, $k); $j > 0; $j--)
            $C[$j] = $C[$j] + $C[$j - 1];
    }
    return $C[$k];
}

// Return the sum of the product of
// consecutive binomial coefficient.
function sumOfproduct($n)
{
    return binomialCoeff(2 * $n, $n - 1);
}

// Driver Code
$n = 3;
echo sumOfproduct($n);

// This code is contributed by mits
?>
```

## JavaScript

```javascript
<script>
    // Javascript Program to find sum of
    // product of consecutive
    // Binomial Coefficient.

    let MAX = 100;

    // Find the binomial coefficient
    // up to nth term
    function binomialCoeff(n, k)
    {
        let C = new Array(k + 1);
        C.fill(0);

        // memset(C, 0, sizeof(C));
        C[0] = 1; // nC0 is 1

        for (let i = 1; i <= n; i++)
        {

            // Compute next row of
            // pascal triangle
            // using the previous row
            for (let j = Math.min(i, k); j > 0; j--)
                C[j] = C[j] + C[j - 1];
        }

        return C[k];
  }

  // Return the sum of the
  // product of consecutive
  // binomial coefficient.
  function sumOfproduct(n)
  {
      return binomialCoeff(2 * n, n - 1);
  }

  let n = 3;
  document.write(sumOfproduct(n));

// This code is contributed by suresh07.
</script>
```

## 输出

```

```