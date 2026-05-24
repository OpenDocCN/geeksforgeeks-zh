# 将厘米转换为像素的程序

> 原文：[https://www.geeksforgeeks.org/program-to-convert-centimeters-to-pixels/](https://www.geeksforgeeks.org/program-to-convert-centimeters-to-pixels/)

给定一个整数`厘米`，表示以[厘米](https://en.wikipedia.org/wiki/Centimetre)测量的长度，任务是将其转换为以[像素](https://en.wikipedia.org/wiki/Pixel)测量的等值。

**示例：**

> **输入：** `厘米` = 10
> **输出：** `像素` = 377.95
>
> **输入：** `厘米` = 5.5
> **输出：** `像素` = 207.87

方法：可根据以下数学关系解决问题：

> 1 [英寸](https://en.wikipedia.org/wiki/Inch) = 96 px
> 1 英寸 = 2.54 cm
> 因此，2.54cm = 96 px
> => 1cm = (96/2.54)px
> => N cm = ((N * 96)/2.54)px

以下是上述方法的实现：

## C++

```cpp
// C++ program to convert centimeter to pixels
#include <bits/stdc++.h>
using namespace std;

// Function to convert
// centimeters to pixels
void Conversion(double centi)
{

    double pixels = (96 * centi) / 2.54;
    cout << fixed << setprecision(2) << pixels;
}

// Driver Code
int main()
{

    double centi = 15;
    Conversion(centi);
    return 0;
}
```

## Java

```java
// Java program to convert
// centimeter to pixels

import java.io.*;

class GFG {

    // Function to convert
    // centimeters to pixels
    static double Conversion(double centi)
    {
        double pixels = (96 * centi) / 2.54;
        System.out.println(pixels);
        return 0;
    }

    // Driver Code
    public static void main(String args[])
    {
        int centi = 15;
        Conversion(centi);
    }
}
```

## Python 3

```python
# Python program to convert
# centimeters to pixels

# Function to convert
# centimeters to pixels
def Conversion(centi):

    pixels = ( 96 * centi)/2.54
    print ( round(pixels, 2))
# Driver Code
centi = 15
Conversion(centi)
```

## C#

```csharp
// C# program to convert
// centimeter to pixels
using System;

class GFG {

    // Function to convert
    // centimeter to pixels
    static double Conversion(double centi)
    {
        double pixels = (96 * centi) / 2.54;
        Console.WriteLine(pixels);
        return 0;
    }

    // Driver Code
    public static void Main()
    {
        double centi = 15;
        Conversion(centi);
    }
}
```

## PHP

```php
<?php

// PHP program to convert
// centimeter to Pixels

// Function to convert
// centimeter to pixels
function Conversion($centi)
{
    $pixels = (96 * $centi)/2.54;
    echo($pixels . "\n");
}

// Driver Code
$centi = 15;
Conversion($centi);
?>
```

## JavaScript

```javascript
<script>

// JavaScript program to convert
// centimeter to pixels
function Conversion(centi)
    {
        let pixels = (96 * centi) / 2.54;
        document.write(pixels);
        return 0;
    }         

// Driver Code
        let centi = 15;
        Conversion(centi)

  // This code is contributed by souravghosh0416.
</script>
```

**输出：**

```
566.93
```

**时间复杂度：** `O(1)`
**辅助空间：** `O(1)`