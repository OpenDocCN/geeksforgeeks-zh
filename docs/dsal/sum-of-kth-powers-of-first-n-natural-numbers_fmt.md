# 前 n 个自然数的第 k 次幂之和

> 原文: [https://www.geeksforgeeks.org/sum-of-kth-powers-of-first-n-natural-numbers/](https://www.geeksforgeeks.org/sum-of-kth-powers-of-first-n-natural-numbers/)

给定两个整数 `n` 和 `k`，任务是计算并打印 `1^k + 2^k + 3^k + … + n^k`。

**举例:**

> **输入:** `n = 5`，`k = 2`
> **输出:** `55`
> `1^2 + 2^2 + 3^2 + 4^2 + 5^2 = 1 + 4 + 9 + 16 + 25 = 55`
> **输入:** `n = 10`，`k = 4`
> **输出**

## 方法:

前 n 个自然数平方和的证明:

> `(n+1)^3 – n^3 = 3 * n^2 + 3 * n + 1`
> 令 `n = 1, 2, 3, 4, … n`
> `2^3 – 1^3 = 3 * 1^2 + 3 * 1 + 1` … 方程 1
> `3^3 – 2^3 = 3 * 2^2 + 3 * 2 + 1` … 方程 2
> `4^3 – 3^3 = 3 * 3^2 + 3 * 3 + 1` … 方程 3
> ……
> `(n+1)^3 – n^3 = 3 * n^2 + 3 * n + 1` … 方程 n

将所有方程相加:

> `(n+1)^3 – 1^3 = 3 * (平方项之和) + 3 * (n 项之和) + n`
> `n^3 + 3 * n^2 + 3 * n = 3 * (平方项之和) + (3 * n * (n + 1)) / 2 + n`
> 平方项之和 = `(n * (n + 1) * (2 * n + 1)) / 6`

同样，立方体的证明可以通过取:
来显示

> `(n+1)^4 – n^4 = 4 * n^3 + 6 * n^2 + 4 * n + 1`
> 如果我们继续这个过程 `n^5`，`n^6`，`n^7` … `n^k`
> 平方和，
> `(n+1)^3 – 1^3 = C(3,1) * sum(n^2) + C(3,2) * sum(n) + C(3,3)`
> 利用平方和我们可以求出立方体的和，
> `(n+1)^4 – 1^4 = C(4,1) * sum(n^3) + C(4,2) * sum(n^2) + C(4,3) * sum(n) + C(4,4)`

同样，对于第 k 次幂和，

> `(n+1)^k – 1^k = C(k,1) * sum(n^(k–1)) + C(k,2) * sum(n^(k–2)) + … + C(k, k–1) * sum(n^(k-(k-1))) + C(k,k)`

以下是上述方法的实现:

## C++

```cpp
// C++ program to find sum pf k-th powers of
// first n natural numbers.
#include <bits/stdc++.h>
using namespace std;

// A global array to store factorials
const int MAX_K = 15;
long long unsigned int fac[MAX_K];

// Function to calculate the factorials
// of all the numbers upto k
void factorial(int k)
{
    fac[0] = 1;
    for (int i = 1; i <= k + 1; i++) {
        fac[i] = (i * fac[i - 1]);
    }
}

// Function to return the binomial coefficient
long long unsigned int bin(int a, int b)
{

    // nCr = (n! * (n - r)!) / r!
    long long unsigned int ans =
               ((fac[a]) / (fac[a - b] * fac[b]));
    return ans;
}

// Function to return the sum of kth powers of
// n natural numbers
long int sumofn(int n, int k)
{
    int p = 0;
    long long unsigned int num1, temp, arr[1000];
    for (int j = 1; j <= k; j++) {

        // When j is unity
        if (j == 1) {
            num1 = (n * (n + 1)) / 2;

            // Calculating sum(n^1) of unity powers
            // of n; storing sum(n^1) for sum(n^2)
            arr[p++] = num1;

            // If k = 1 then temp is the result
            temp = num1;
        }
        else {
            temp = (pow(n + 1, j + 1) - 1 - n);

            // For finding sum(n^k) removing 1 and
            // n * kCk from (n + 1)^k
            for (int s = 1; s < j; s++) {

                // Removing all kC2 * sum(n^(k - 2))
                // + ... + kCk - 1 * (sum(n^(k - (k - 1))
                temp = temp -
                    (arr[j - s - 1] * bin(j + 1, s + 1));
            }
            temp = temp / (j + 1);

            // Storing the result for next sum of
            // next powers of k
            arr[p++] = temp;
        }
    }
    temp = arr[p - 1];
    return temp;
}

// Driver code
int main()
{
    int n = 5, k = 2;
    factorial(k);
    cout << sumofn(n, k) << "\n";
    return 0;
}
```

## Java

```java
// Java program to find sum pf k-th powers of
// first n natural numbers.

import java.io.*;

class GFG {

// A global array to store factorials
static int MAX_K = 15;
static int fac[] = new int[MAX_K];

// Function to calculate the factorials
// of all the numbers upto k
static void factorial(int k)
{
    fac[0] = 1;
    for (int i = 1; i <= k + 1; i++) {
        fac[i] = (i * fac[i - 1]);
    }
}

// Function to return the binomial coefficient
static  int bin(int a, int b)
{

    // nCr = (n! * (n - r)!) / r!
    int ans =
            ((fac[a]) / (fac[a - b] * fac[b]));
    return ans;
}

// Function to return the sum of kth powers of
// n natural numbers
static int sumofn(int n, int k)
{
    int p = 0;
    int num1, temp;
    int arr[] = new int[1000];
    for (int j = 1; j <= k; j++) {

        // When j is unity
        if (j == 1) {
            num1 = (n * (n + 1)) / 2;

            // Calculating sum(n^1) of unity powers
            // of n; storing sum(n^1) for sum(n^2)
            arr[p++] = num1;

            // If k = 1 then temp is the result
            temp = num1;
        }
        else {
            temp = ((int)Math.pow(n + 1, j + 1) - 1 - n);

            // For finding sum(n^k) removing 1 and
            // n * kCk from (n + 1)^k
            for (int s = 1; s < j; s++) {

                // Removing all kC2 * sum(n^(k - 2))
                // + ... + kCk - 1 * (sum(n^(k - (k - 1))
                temp = temp -
                    (arr[j - s - 1] * bin(j + 1, s + 1));
            }
            temp = temp / (j + 1);

            // Storing the result for next sum of
            // next powers of k
            arr[p++] = temp;
        }
    }
    temp = arr[p - 1];
    return temp;
}

// Driver code

    public static void main (String[] args) {
            int n = 5, k = 2;
    factorial(k);
    System.out.println( sumofn(n, k));
    }
}
// This code is contributed by anuj_67..
```

## Python 3

```python
# Python3 program to find the sum pf k-th
# powers of first n natural numbers

# global array to store factorials
MAX_K = 15
fac = [1 for i in range(MAX_K)]

# function to calculate the factorials
# of all the numbers upto k
def factorial(k):
    fac[0] = 1
    for i in range(1, k + 2):
        fac[i] = (i * fac[i - 1])

# function to return the binomial coeff
def bin(a, b):

    # nCr=(n!*(n-r)!)/r!
    ans = fac[a] // (fac[a - b] * fac[b])
    return ans

# function to return the sum of the kth
# powers of n natural numbers
def sumofn(n, k):
    p = 0
    num1, temp = 1, 1
    arr = [1 for i in range(1000)]

    for j in range(1, k + 1):

        # when j is 1
        if j == 1:
            num1 = (n * (n + 1)) // 2

            # calculating sum(n^1) of unity powers
            #of n storing sum(n^1) for sum(n^2)
            arr[p] = num1
            p += 1

            # if k==1 then temp is the result
        else:
            temp = pow(n + 1, j + 1) - 1 - n

            # for finding sum(n^k) removing 1 and
            # n*KCk from (n+1)^k
            for s in range(1, j):

                # Removing all kC2 * sum(n^(k - 2))
                # + ... + kCk - 1 * (sum(n^(k - (k - 1))
                temp = temp - (arr[j - s - 1] *
                               bin(j + 1, s + 1))
            temp = temp // (j + 1)

            # storing the result for next sum
            # of next powers of k
            arr[p] = temp
            p += 1
    temp = arr[p - 1]
    return temp

# Driver code
n, k = 5, 2
factorial(k)
print(sumofn(n, k))

# This code is contributed by Mohit kumar 29
```

## C#

```csharp
// C# program to find sum pf k-th powers of
// first n natural numbers.

using System;

class GFG {

// A global array to store factorials
static int MAX_K = 15;
static int []fac = new int[MAX_K];

// Function to calculate the factorials
// of all the numbers upto k
static void factorial(int k)
{
    fac[0] = 1;
    for (int i = 1; i <= k + 1; i++) {
        fac[i] = (i * fac[i - 1]);
    }
}

// Function to return the binomial coefficient
static int bin(int a, int b)
{

    // nCr = (n! * (n - r)!) / r!
    int ans =
            ((fac[a]) / (fac[a - b] * fac[b]));
    return ans;
}

// Function to return the sum of kth powers of
// n natural numbers
static int sumofn(int n, int k)
{
    int p = 0;
    int num1, temp;
    int []arr = new int[1000];
    for (int j = 1; j <= k; j++) {

        // When j is unity
        if (j == 1) {
            num1 = (n * (n + 1)) / 2;

            // Calculating sum(n^1) of unity powers
            // of n; storing sum(n^1) for sum(n^2)
            arr[p++] = num1;

            // If k = 1 then temp is the result
            temp = num1;
        }
        else {
            temp = ((int)Math.Pow(n + 1, j + 1) - 1 - n);

            // For finding sum(n^k) removing 1 and
            // n * kCk from (n + 1)^k
            for (int s = 1; s < j; s++) {

                // Removing all kC2 * sum(n^(k - 2))
                // + ... + kCk - 1 * (sum(n^(k - (k - 1))
                temp = temp -
                    (arr[j - s - 1] * bin(j + 1, s + 1));
            }
            temp = temp / (j + 1);

            // Storing the result for next sum of
            // next powers of k
            arr[p++] = temp;
        }
    }
    temp = arr[p - 1];
    return temp;
}

    // Driver code
    public static void Main () {
            int n = 5, k = 2;
            factorial(k);
            Console.WriteLine(sumofn(n, k));
    }
    // This code is contributed by Ryuga
}
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```php
<?php
// PHP program to find sum pf k-th powers
// of first n natural numbers.

// A global array to store factorial
$MAX_K = 15;
$fac[$MAX_K] = array();

// Function to calculate the factorials
// of all the numbers upto k
function factorial($k)
{
    global $fac;
    $fac[0] = 1;
    for ($i = 1; $i <= $k + 1; $i++)
    {
        $fac[$i] = ($i * $fac[$i - 1]);
    }
}

// Function to return the binomial
// coefficient
function bin($a, $b)
{
    global $MAX_K;
    global $fac;

    // nCr = (n! * (n - r)!) / r!
    $ans = (($fac[$a]) / ($fac[$a - $b] *
                          $fac[$b]));
    return $ans;
}

// Function to return the sum of kth
// powers of n natural numbers
function sumofn($n, $k)
{
    $p = 0; $num1; $temp;
    $arr[1000] = array();
    for ($j = 1; $j <= $k; $j++)
    {

        // When j is unity
        if ($j == 1)
        {
            $num1 = ($n * ($n + 1)) / 2;

            // Calculating sum(n^1) of unity powers
            // of n; storing sum(n^1) for sum(n^2)
            $arr[$p++] = $num1;

            // If k = 1 then temp is the result
            $temp = $num1;
        }
        else
        {
            $temp = (pow($n + 1, $j + 1) - 1 - $n);

            // For finding sum(n^k) removing 1
            // and n * kCk from (n + 1)^k
            for ($s = 1; $s < $j; $s++)
            {

                // Removing all kC2 * sum(n^(k - 2))
                // + ... + kCk - 1 * (sum(n^(k - (k - 1))
                $temp = $temp - ($arr[$j - $s - 1] *
                                  bin($j + 1, $s + 1));
            }
            $temp = $temp / ($j + 1);

            // Storing the result for next
            // sum of next powers of k
            $arr[$p++] = $temp;
        }
    }
    $temp = $arr[$p - 1];
    return $temp;
}

// Driver code
$n = 5;
$k = 2;
factorial($k);
echo sumofn($n, $k), "\n";

// This code is contributed by Sachin
?>
```

## java 描述语言

```javascript
<script>

// Javascript program to find sum pf k-th powers of
// first n natural numbers.   

// A global array to store factorials
    var MAX_K = 15;
    var fac = Array(MAX_K).fill(0);

    // Function to calculate the factorials
    // of all the numbers upto k
    function factorial(k) {
        fac[0] = 1;
        for (i = 1; i <= k + 1; i++) {
            fac[i] = (i * fac[i - 1]);
        }
    }

    // Function to return the binomial coefficient
    function bin(a , b) {

        // nCr = (n! * (n - r)!) / r!
        var ans = ((fac[a]) / (fac[a - b] * fac[b]));
        return ans;
    }

    // Function to return the sum of kth powers of
    // n natural numbers
    function sumofn(n , k) {
        var p = 0;
        var num1, temp;
        var arr = Array(1000).fill(0);
        for (j = 1; j <= k; j++) {

            // When j is unity
            if (j == 1) {
                num1 = (n * (n + 1)) / 2;

                // Calculating sum(n^1) of unity powers
                // of n; storing sum(n^1) for sum(n^2)
                arr[p++] = num1;

                // If k = 1 then temp is the result
                temp = num1;
            } else {
                temp = (parseInt( Math.pow(n + 1, j + 1) - 1 - n));

                // For finding sum(n^k) removing 1 and
                // n * kCk from (n + 1)^k
                for (s = 1; s < j; s++) {

                    // Removing all kC2 * sum(n^(k - 2))
                    // + ... + kCk - 1 * (sum(n^(k - (k - 1))
                    temp = temp - (arr[j - s - 1] * bin(j + 1, s + 1));
                }
                temp = temp / (j + 1);

                // Storing the result for next sum of
                // next powers of k
                arr[p++] = temp;
            }
        }
        temp = arr[p - 1];
        return temp;
    }

    // Driver code

        var n = 5, k = 2;
        factorial(k);
        document.write(sumofn(n, k));

// This code contributed by Rajput-Ji

</script>
```

**Output:**

```output

```