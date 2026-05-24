# 程序求一个数列的和 1/1!+ 2/2!+ 3/3!+ 4/4!+…….+ n/n！

> 原文: [https://www.geeksforgeeks.org/program-to-find-the-sum-of-a-series-11-22-33-44-nn/](https://www.geeksforgeeks.org/program-to-find-the-sum-of-a-series-11-22-33-44-nn/)

你已经得到了 `1/1! + 2/2! + 3/3! + 4/4! + …… + n/n!`，求出直到第 `n` 项的级数和。

## 示例

```
Input : n = 5
Output : 2.70833

Input : n = 7
Output : 2.71806
```

一个**简单的解决方案**就是给一个个电脑术语。对于每个项，找到它对应的阶乘值。
一个**有效的解决方案**是在同一个循环中进行阶乘计算。

## C++ 实现

```
// CPP program to print
// the sum of series
#include<bits/stdc++.h>
using namespace std;

// function to calculate
// sum of given series
double sumOfSeries(double num)
{
    double res = 0, fact = 1;
    for (int i = 1; i <= num; i++)
    {
        // fact variable store
        // factorial of the i
        fact = fact * i;

        res = res + (i / fact);
    }
    return(res);
}

// Driver Code
int main()
{
    double n = 5;
    cout << "Sum: " << sumOfSeries(n);
    return 0;
}
```

## Java 实现

```
// Java program to print
// the sum of series

import java.io.*;
import java.lang.*;

class GFG
{
    public static double sumOfSeries(double num)
    {
        double res = 0, fact = 1;
        for (int i = 1; i <= num; i++)
        {
            // fact variable store
            // factorial of the i
            fact = fact * i;

            res = res + (i / fact);
        }
        return(res);
    }

    // Driver Code
    public static void main (String[] args)
    {
        double n = 5;
        System.out.println("Sum: " + sumOfSeries(n));
    }
}

// This code is contributed by
// Mohit Gupta_OMG <(0_o)>
```

## Python 实现

```
# Python code to find smallest K-digit
# number divisible by X

def sumOfSeries(num):

    # Computing MAX
    res = 0
    fact = 1

    for i in range(1, num+1):
        fact *= i
        res = res + (i/ fact)

    return res

n = 5
print("Sum: ", sumOfSeries(n))

# Code contributed by
# Mohit Gupta_OMG <(0_o)>
```

## C# 实现

```
// C# program to print the sum of series
using System;

class GFG
{
    public static float sumOfSeries(double num)
    {
        float res = 0, fact = 1;
        for (int i = 1; i <= num; i++)
        {
            // fact variable store
            // factorial of the i
            fact = fact * i;

            res = res + (i / fact);
        }
        return(res);
    }

    // Driver Code
    public static void Main ()
    {
        double n = 5;
        Console.Write("Sum: " + sumOfSeries(n));
    }
}

// This code is contributed by vt_m.
```

## PHP 实现

```
<?php
// PHP program to print
// the sum of series

// Function to calculate
// sum of given series
function sumOfSeries($num)
{
    $res = 0; $fact = 1;
    for ($i = 1; $i <= $num; $i++)
    {
        // fact variable store
        // factorial of the i
        $fact = $fact * $i;

        $res = $res + ($i / $fact);
    }
    return ($res);
}

// Driver Code
$n = 5;
echo("Sum: " . sumOfSeries($n));

// This code is contributed by Ajit.
?>
```

## JavaScript 实现

```
<script>
// javascript program to print
// the sum of series
function sumOfSeries(num)
{
    var res = 0, fact = 1;
    for (i = 1; i <= num; i++)
    {

        // fact variable store
        // factorial of the i
        fact = fact * i;
        res = res + (i / fact);
    }
    return(res);
}

// Driver Code
var n = 5;
document.write("Sum: " + sumOfSeries(n).toFixed(5));

// This code is contributed by Amit Katiyar
</script>
```

## 输出

```
Sum: 2.70833
```

时间复杂度: `O(n)`
辅助空间: `O(1)`

本文由 **R_Raj** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [write.geeksforgeeks.org](https://write.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `review-team@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。