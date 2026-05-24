# 计算等边三角形内圆面积和周长的程序

> 原文：[`https://www.geeksforgeeks.org/program-to-calculate-the-area-and-perimeter-of-incircle-of-an-equilateral-triangle/`](https://www.geeksforgeeks.org/program-to-calculate-the-area-and-perimeter-of-incircle-of-an-equilateral-triangle/)

给定等边三角形的边长，任务是求给定等边三角形的内圆的面积和周长。

## 示例

```
Input: side = 6 
Output: Area = 9.4. Perimeter = 10.88

Input: side = 9
Output: Area = 21.21, Perimeter = 16.32
```

## 内圆的特性

*   内圆的中心与三角形的中心相同，即等边三角形的中点相交的点。
*   等边三角形的内切圆是通过等边三角形的边的中点构成的。
*   等边三角形内圆的内切圆半径可以使用以下公式计算：
    ```
    r = a / (2 * sqrt(3))
    ```
    其中`a`为等边三角形边长。
*   下图显示了一个内圆为的等边三角形。

## 方法

圆的面积 = `π * r^2` 和圆的周长 = `2 * π * r`，其中 `r` 是给定圆的半径。

同样等边三角形的内圆半径 = (等边三角形的边) / 3。
因此，

1.  使用内切圆半径计算内圆面积的公式为：`Area = π * (a^2 / 12)`
2.  使用内切圆半径计算内圆周长的公式为：`Perimeter = 2 * π * (a / (2 * sqrt(3)))`

## C

```c
// C program to find the area of Inscribed circle 
// of equilateral triangle
#include <math.h>
#include <stdio.h>
#define PI 3.14159265

// function to find area of inscribed circle
float area_inscribed(float a)
{
    return (a * a * (PI / 12));
}

// function to find Perimeter of inscribed circle
float perm_inscribed(float a)
{
    return (PI * (a / sqrt(3)));
}

// Driver code
int main()
{
    float a = 6;
    printf("Area of inscribed circle is :%f\n",
           area_inscribed(a));
    printf("Perimeter of inscribed circle is :%f",
           perm_inscribed(a));
    return 0;
}
```

## Java

```java
// Java code to find the area of inscribed
// circle of equilateral triangle
import java.lang.*;

class GFG {
    static double PI = 3.14159265;

    // function to find the area of
    // inscribed circle
    public static double area_inscribed(double a)
    {
        return (a * a * (PI / 12));
    }

    // function to find the perimeter of
    // inscribed circle
    public static double perm_inscribed(double a)
    {
        return (PI * (a / Math.sqrt(3)));
    }

    // Driver code
    public static void main(String[] args)
    {
        double a = 6.0;
        System.out.println("Area of inscribed circle is :"
                           + area_inscribed(a));
        System.out.println("\nPerimeter of inscribed circle is :"
                           + perm_inscribed(a));
    }
}
```

## Python 3

```python
# Python3 code to find the area of inscribed 
# circle of equilateral triangle
import math
PI = 3.14159265

# Function to find the area of 
# inscribed circle
def area_inscribed(a):
    return (a * a * (PI / 12))

# Function to find the perimeter of 
# inscribed circle
def perm_inscribed(a):
    return ( PI * (a / math.sqrt(3) ) )

# Driver code
a = 6.0
print("Area of inscribed circle is :% f"
                    % area_inscribed(a))
print("\nPerimeter of inscribed circle is :% f"
                    % perm_inscribed(a))
```

## C#

```csharp
// C# code to find the area of
// inscribed circle
// of equilateral triangle
using System;

class GFG {
    static double PI = 3.14159265;

    // function to find the area of
    // inscribed circle
    public static double area_inscribed(double a)
    {
        return (a * a * (PI / 12));
    }

    // function to find the perimeter of
    // inscribed circle
    public static double perm_inscribed(double a)
    {
        return (PI * (a / Math.Sqrt(3)));
    }

    // Driver code
    public static void Main()
    {
        double a = 6.0;
        Console.Write("Area of inscribed circle is :"
                      + area_inscribed(a));
        Console.Write("\nPerimeter of inscribed circle is :"
                      + perm_inscribed(a));
    }
}
```

## PHP

```php
<?php
// PHP program to find the 
// area of inscribed 
// circle of equilateral triangle
$PI = 3.14159265;

// function to find area of 
// inscribed circle
function area_inscribed($a)
{
    global $PI;
    return ($a * $a * ($PI / 12));
}

// function to find perimeter of 
// inscribed circle
function perm_inscribed($a)
{
    global $PI;
    return ( $PI * ( $a / sqrt(3) ) );
}

// Driver code
$a = 6;
echo("Area of inscribed circle is :");
echo(area_inscribed($a));
echo("Perimeter of inscribed circle is :");
echo(perm_inscribed($a));
?>
```

## 输出

```
Area of inscribed circle is :9.424778
Perimeter of inscribed circle is :10.882796
```