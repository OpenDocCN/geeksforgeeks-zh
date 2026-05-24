# 程序求数列的和(1/a + 2/a^2 + 3/a^3 + … + n/a^n)

> 原文:[https://www . geesforgeks . org/program-to-find-the-sum-series-1-a-2-a2-3-a3-n-an/](https://www.geeksforgeeks.org/program-to-find-the-sum-of-the-series-1-a-2-a2-3-a3-n-an/)

给定两个整数`a`和`n`。任务是找到系列`1/a+2/a^2+3/a^3+…+n/a^n`的和。

**举例:**

> **输入:** `a = 3`，`n = 3`
> **输出:** `0.6666667`
> 级数为 `1/3 + 1/9 + 1/27` 也就是
> 等于 `0.6666667`
> **输入:** `a = 5`，`n = 4`
> **输出:** `0.31039998`

**逼近:** [从 **1 到 n** 运行一个循环](https://www.geeksforgeeks.org/loops-in-java/)，通过计算`项= (i / a^i )`得到数列的`i-th`项。将所有生成的术语相加，这就是最终答案。

以下是上述方法的实施:

## C++

```cpp
// C++ program to find the sum of
// the given series
#include <stdio.h>
#include <math.h>
#include <iostream>

using namespace std;

// Function to return the
// sum of the series
float getSum(int a, int n)
{
    // variable to store the answer
    float sum = 0;
    for (int i = 1; i <= n; ++i)
    {

        // Math.pow(x, y) returns x^y
        sum += (i / pow(a, i));
    }
    return sum;
}

// Driver code
int main()
{
    int a = 3, n = 3;

    // Print the sum of the series
    cout << (getSum(a, n));
    return 0;
}

// This code is contributed
// by Sach_Code
```

## Java

```java
// Java program to find the sum of the given series
import java.util.Scanner;

public class HelloWorld {

    // Function to return the sum of the series
    public static float getSum(int a, int n)
    {
        // variable to store the answer
        float sum = 0;
        for (int i = 1; i <= n; ++i) {

            // Math.pow(x, y) returns x^y
            sum += (i / Math.pow(a, i));
        }
        return sum;
    }

    // Driver code
    public static void main(String[] args)
    {
        int a = 3, n = 3;

        // Print the sum of the series
        System.out.println(getSum(a, n));
    }
}
```

## Python 3

```python
# Python 3 program to find the sum of
# the given series
import math

# Function to return the
# sum of the series
def getSum(a, n):

    # variable to store the answer
    sum = 0;
    for i in range (1, n + 1):

        # Math.pow(x, y) returns x^y
        sum += (i / math.pow(a, i));

    return sum;

# Driver code
a = 3; n = 3;

# Print the sum of the series
print(getSum(a, n));

# This code is contributed
# by Akanksha Rai
```

## C\#

```csharp
// C# program to find the sum
// of the given series
using System;

class GFG
{

// Function to return the sum
// of the series
public static double getSum(int a, int n)
{
    // variable to store the answer
    double sum = 0;
    for (int i = 1; i <= n; ++i)
    {

        // Math.pow(x, y) returns x^y
        sum += (i / Math.Pow(a, i));
    }
    return sum;
}

// Driver code
static public void Main ()
{
    int a = 3, n = 3;

    // Print the sum of the series
    Console.WriteLine(getSum(a, n));
}
}

// This code is contributed by jit_t
```

## PHP

```php
<?php
// PHP program to find the
// sum of the given series

// Function to return the
// sum of the series
function getSum($a, $n)
{
    // variable to store the answer
    $sum = 0;
    for ($i = 1; $i <= $n; ++$i)
    {

        // Math.pow(x, y) returns x^y
        $sum += ($i / pow($a, $i));
    }
    return $sum;
}

// Driver code
$a = 3;
$n = 3;

// Print the sum of the series
echo (getSum($a, $n));

// This code is contributed by akt_mit
?>
```

## JavaScript

```javascript
<script>

// Javascript program to find the sum of the given series

    // Function to return the sum of the series
    function getSum( a, n) {
        // variable to store the answer
        let sum = 0;
        for (let i = 1; i <= n; ++i) {

            // Math.pow(x, y) returns x^y
            sum += (i / Math.pow(a, i));
        }
        return sum;
    }

    // Driver code

        let a = 3, n = 3;

        // Print the sum of the series
        document.write(getSum(a, n).toFixed(7));

// This code contributed by Princi Singh

</script>
```

**Output:**

```
0.6666667
```