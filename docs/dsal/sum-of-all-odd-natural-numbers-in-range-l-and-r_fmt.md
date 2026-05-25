# L 和 R 范围内所有奇数自然数之和

> 原文: [https://www.geeksforgeeks.org/sum-of-all-odd-natural-numbers-in-range-l-and-r/](https://www.geeksforgeeks.org/sum-of-all-odd-natural-numbers-in-range-l-and-r/)

给定两个整数 `L` 和 `R`，任务是求 `L` 和 `R` 范围内所有奇数自然数的和。

`例`:

```
Input: L = 2, R = 5
Output: 8
3 + 5 = 8

Input: L = 7, R = 13
Output: 40
```

一种天真的方法是从 `L` 遍历到 `R`，对元素求和得到答案。
一个有效的方法是用公式计算所有奇数自然数的和直到 `R` 和 `L-1`，再减去 `sum(R) - sum(L-1)`。
以下是上述方法的实施：

## C++

```cpp
// C++ program to print the sum
// of all numbers in range L and R
#include <bits/stdc++.h>
using namespace std;

// Function to return the sum of
// all odd natural numbers
int sumOdd(int n)
{
    int terms = (n + 1) / 2;
    int sum = terms * terms;
    return sum;
}

// Function to return the sum
// of all odd numbers in range L and R
int suminRange(int l, int r)
{
    return sumOdd(r) - sumOdd(l - 1);
}

// Driver Code
int main()
{
    int l = 2, r = 5;
    cout << "Sum of odd natural numbers from L to R is "
         << suminRange(l, r);

    return 0;
}
```

## Java

```java
// Java program to print the sum
// of all numbers in range L and R

import java.io.*;

class GFG {

// Function to return the sum of
// all odd natural numbers
static int sumOdd(int n)
{
    int terms = (n + 1) / 2;
    int sum = terms * terms;
    return sum;
}

// Function to return the sum
// of all odd numbers in range L and R
static int suminRange(int l, int r)
{
    return sumOdd(r) - sumOdd(l - 1);
}

// Driver Code
public static void main (String[] args) {
            int l = 2, r = 5;
    System.out.print( "Sum of odd natural numbers from L to R is "
        + suminRange(l, r));
    }
}
// This code is contributed by shs..
```

## Python 3

```python
# Python 3 program to print the sum
# of all numbers in range L and R

# Function to return the sum of
# all odd natural numbers
def sumOdd(n):
    terms = (n + 1)//2
    sum1 = terms * terms
    return sum1

# Function to return the sum
# of all odd numbers in range L and R
def suminRange(l, r):
    return sumOdd(r) - sumOdd(l - 1)

# Driver code
l = 2; r = 5
print("Sum of odd natural number",
      "from L to R is", suminRange(l, r))

# This code is contributed by Shrikant13
```

## C\#

```csharp
// C# program to print the sum
// of all numbers in range L and R
using System;

class GFG
{

// Function to return the sum of
// all odd natural numbers
static int sumOdd(int n)
{
    int terms = (n + 1) / 2;
    int sum = terms * terms;
    return sum;
}

// Function to return the sum
// of all odd numbers in range L and R
static int suminRange(int l, int r)
{
    return sumOdd(r) - sumOdd(l - 1);
}

// Driver Code
public static void Main ()
{
    int l = 2, r = 5;
    Console.WriteLine( "Sum of odd natural numbers " +
                "from L to R is " + suminRange(l, r));
}
}

// This code is contributed by shs..
```

## PHP

```php
<?php
//PHP program to print the sum
// of all numbers in range L and R
// Function to return the sum of
// all odd natural numbers
function sumOdd($n)
{
    $terms = (int)($n + 1) / 2;
    $sum = $terms * $terms;
    return $sum;
}

// Function to return the sum
// of all odd numbers in range L and R
function suminRange($l, $r)
{
    return sumOdd($r) - sumOdd($l - 1);
}

// Driver Code

    $l = 2;
    $r = 5;
    echo "Sum of odd natural numbers from L to R is ",
         suminRange($l, $r);

?>
```

## JavaScript

```javascript
<script>

//JavaScript program to print the sum
// of all numbers in range L and R

// Function to return the sum of
// all odd natural numbers
function sumOdd(n)
{
    terms = (n + 1) / 2;
    sum = terms * terms;
    return sum;
}

// Function to return the sum
// of all odd numbers in range L and R
function suminRange(l, r)
{
    return sumOdd(r) - sumOdd(l - 1);
}

// Driver Code

let    l = 2;
let    r = 5;
    document.write("Sum of odd natural numbers from L to R is "+
        suminRange(l, r));

// This code is contributed by sravan kumar

</script>
```

`Output:`

```
Sum of odd natural numbers from L to R is 8
```