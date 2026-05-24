# 两个浮点数或双数的模数

> 原文:[https://www . geesforgeks . org/module-two-float-double-numbers/](https://www.geeksforgeeks.org/modulus-two-float-double-numbers/)

给定两个浮点数，求余数。

**示例:**

> **输入** : a = 36.5，b = 5.0
> **输出:** 1.5
> 
> **输入:** a = 9.7，b = 2.3
> T3】输出: 0.5

一个**简单的解决方法**就是做重复减法。

## C++

```cpp
// C++ program to find modulo of floating
// point numbers.
#include <bits/stdc++.h>
using namespace std;

double findMod(double a, double b)
{
    double mod;
    // Handling negative values
    if (a < 0)
        mod = -a;
    else
        mod =  a;
    if (b < 0)
        b = -b;

    // Finding mod by repeated subtraction

    while (mod >= b)
        mod = mod - b;

    // Sign of result typically depends
    // on sign of a.
    if (a < 0)
        return -mod;

    return mod;
}

// Driver Function
int main()
{
    double a = 9.7, b = 2.3;
    cout << findMod(a, b);
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to find modulo of floating
// point numbers

class GFG
{
    static double findMod(double a, double b)
    {
        // Handling negative values
        if (a < 0)
            a = -a;
        if (b < 0)
            b = -b;

        // Finding mod by repeated subtraction
        double mod = a;
        while (mod >= b)
            mod = mod - b;

        // Sign of result typically depends
        // on sign of a.
        if (a < 0)
            return -mod;

        return mod;
    }

    // Driver code
    public static void main (String[] args)
    {
        double a = 9.7, b = 2.3;
        System.out.print(findMod(a, b));
    }
}

// This code is contributed by Anant Agarwal.
```

## 蟒蛇 3

```cpp
# Python3 program to find modulo
# of floating point numbers.

def findMod(a, b):

    # Handling negative values
    if (a < 0):
        a = -a
    if (b < 0):
        b = -b

    # Finding mod by repeated subtraction
    mod = a
    while (mod >= b):
        mod = mod - b

    # Sign of result typically
    # depends on sign of a.
    if (a < 0):
        return -mod

    return mod

# Driver code
a = 9.7; b = 2.3
print(findMod(a, b))

# This code is contributed by Anant Agarwal.
```

## C#

```cpp
// C# program to find modulo of floating
// point numbers
using System;

class GFG {

    static double findMod(double a, double b)
    {

        // Handling negative values
        if (a < 0)
            a = -a;
        if (b < 0)
            b = -b;

        // Finding mod by repeated subtraction
        double mod = a;
        while (mod >= b)
            mod = mod - b;

        // Sign of result typically depends
        // on sign of a.
        if (a < 0)
            return -mod;

        return mod;
    }

    // Driver code
    public static void Main ()
    {

        double a = 9.7, b = 2.3;

        Console.WriteLine(findMod(a, b));
    }
}

// This code is contributed by vt_m.
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```cpp
<?php
// PHP program to find modulo 
// of floatingpoint numbers.

function findMod($a, $b)
{

    // Handling negative values
    if ($a < 0)
        $a = -$a;
    if ($b < 0)
        $b = -$b;

    // Finding mod by repeated
    // subtraction
    $mod = $a;
    while ($mod >= $b)
        $mod = $mod - $b;

    // Sign of result typically
    // depends on sign of a.
    if ($a < 0)
        return -$mod;

    return $mod;
}

    // Driver Code
    $a = 9.7; $b = 2.3;
    echo findMod($a, $b);

// This code is contributed by anuj_65.
?>
```

## java 描述语言

```cpp
<script>

// Javascript program to find
// modulo of floating point numbers.

function findMod(a, b)
{
    let mod;
    // Handling negative values
    if (a < 0)
        mod = -a;
    else
        mod =  a;
    if (b < 0)
        b = -b;

    // Finding mod by
    // repeated subtraction

    while (mod >= b)
        mod = mod - b;

    // Sign of result typically
    // depends on sign of a.
    if (a < 0)
        return -mod;

    return mod;
}

// Driver Function

    let a = 9.7, b = 2.3;
    document.write(findMod(a, b));

//This code is contributed by Mayank Tyagi
</script>
```

**输出:**

```cpp
0.5
```

我们可以使用内置的 [fmod 函数](https://www.geeksforgeeks.org/floating-point-manipulation-math-h/)来求两个浮点数的模。

## C++

```cpp
// CPP program to find modulo of floating
// point numbers using library function.
#include <bits/stdc++.h>
using namespace std;

// Driver Function
int main()
{
    double a = 9.7, b = 2.3;
    cout << fmod(a, b);
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// JAVA program to find modulo of floating
// point numbers using library function.
import java.util.*;

class GFG{

// Driver Function
public static void main(String[] args)
{
    double a = 9.7, b = 2.3;
    System.out.print((a % b));
}
}

// This code contributed by umadevi9616
```

## 蟒蛇 3

```cpp
# Python3 program to find modulo of floating
# point numbers using library function.
from math import fmod

# Driver code
if __name__ == '__main__':

    a = 9.7
    b = 2.3

    print(fmod(a, b))

# This code is contributed by mohit kumar 29
```

## C#

```cpp
// C# program to find modulo of floating
// point numbers using library function.
using System;

class GFG{

static void Main()
{
    double a = 9.7;
    double b = 2.3;
    Console.WriteLine(a % b);
}
}

// This code is contributed by mukesh07
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```cpp
<?php
// PHP program to find modulo of
// floating point numbers using
// library function.

// Driver Code
$a = 9.7; $b = 2.3;
echo fmod($a, $b);

// This code is contributed
// by inder_verma
?>
```

## java 描述语言

```cpp
<script>

// Javascript program to find modulo of
// floating point numbers using
// library function.

// Driver Code
let a = 9.7;
let b = 2.3;
document.write(a%b);

// This code is contributed by mohan pavan

</script>
```

**输出:**

```cpp
0.5
```