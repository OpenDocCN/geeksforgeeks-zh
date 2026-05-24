# C# |数学。Sinh()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-math-sinh-method/](https://www.geeksforgeeks.org/c-sharp-math-sinh-method/)

***数学。Sinh()*** 是内置的数学类方法，它返回给定的双曲正弦值参数(指定角度)。
**语法:**

```cs
public static double Sinh(double num)
```

**参数:**

> **num:** 是要返回双曲正弦的数字，该参数的类型是*系统。双*。

**返回值:**该方法返回类型为*系统的数字的双曲正弦值。双*。如果 num 等于 NegativeInfinity、PositiveInfinity 或 NaN，此方法将返回一个等于 num 的 Double。

```cs
Input  : num = 60.0
Output : 5.71003695E25
```

下面的程序说明了数学。辛法:
**程序一:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the
// Math.Sinh()
using System;

class GFG {

    // Main Method
    public static void Main(String[] args)
    {

        double num1 = 78.8, num2 = 0.0, num3 = 1.0;

        // It returns the hyperbolic sine of specified
        // angle in radian
        double sinhvalue = Math.Sinh(num1);
        Console.WriteLine("The sinh of num1 = " + sinhvalue);

        sinhvalue = Math.Sinh(num2);
        Console.WriteLine("The sinh of num2 = " + sinhvalue);

        sinhvalue = Math.Sinh(num3);
        Console.WriteLine("The sinh of num3 = " + sinhvalue);
    }
}
```

**Output:** 

```cs
The sinh of num1 = 8.34401696285252E+33
The sinh of num2 = 0
The sinh of num3 = 1.1752011936438
```

**节目 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the
// Math.Sinh() Method
using System;

class GFG {

    // Main Method
    public static void Main(String[] args)
    {

        double num1 = (30 * (Math.PI)) / 180, num2 = 11.0, num3 = 45.0;

        // It returns the hyperbolic sine of
        // angle in radian
        double sinhvalue = Math.Sinh(num1);
        Console.WriteLine("The sinh of num1 = " + sinhvalue);

        sinhvalue = Math.Sinh(num2);
        Console.WriteLine("The sinh of num2 = " + sinhvalue);

        sinhvalue = Math.Sinh(num3);
        Console.WriteLine("The sinh of num3 = " + sinhvalue);
    }
}
```

**Output:** 

```cs
The sinh of num1 = 0.54785347388804
The sinh of num2 = 29937.0708492481
The sinh of num3 = 1.74671355287425E+19
```