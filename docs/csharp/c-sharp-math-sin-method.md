# C# |数学。Sin()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-math-sin-method/](https://www.geeksforgeeks.org/c-sharp-math-sin-method/)

**数学。Sin()** 是一个内置的数学类方法，它返回给定双值参数(指定角度)的正弦值。

**语法:**

```cs
public static double Sin(double num)
```

**参数:**

> **num:** 是要返回正弦的角度(以弧度为单位)，该参数的类型为*系统。双*。

**返回值:**返回类型为**系统的数字的正弦值。双**。如果 num 等于*否定有限性、肯定有限性或 NaN* ，则该方法返回 *NaN* 。

下面是说明数学的程序。Sin()方法。

**程序 1:** 展示数学的工作原理。Sin()方法。

```cs
// C# program to demonstrate working
// Math.Sin() method
using System;

class Geeks {

    // Main Method
    public static void Main(String []args)
    {
        double a = 30;

        // converting value to radians
        double b = (a * (Math.PI)) / 180;

        // using method and displaying result
        Console.WriteLine(Math.Sin(b));
        a = 45;

        // converting value to radians
        b = (a * (Math.PI)) / 180;

        // using method and displaying result
        Console.WriteLine(Math.Sin(b));
        a = 60;

        // converting value to radians
        b = (a * (Math.PI)) / 180;

        // using method and displaying result
        Console.WriteLine(Math.Sin(b));
        a = 90;

        // converting value to radians
        b = (a * (Math.PI)) / 180;

        // using method and displaying result
        Console.WriteLine(Math.Sin(b));
    }
}
```

**Output:**

```cs
0.5
0.707106781186547
0.866025403784439
1

```

**程序 2:** 展示数学的工作原理。Sin()方法时的自变量是 *NaN 或无穷大*。

```cs
// C# program to demonstrate working
// Math.Sin() method in infinity case
using System;

class Geeks {

    // Main Method
    public static void Main(String []args)
    {

        double positiveInfinity = Double.PositiveInfinity;

        double negativeInfinity = Double.NegativeInfinity;

        double nan = Double.NaN;
        double result;

        // Here argument is negative infinity,
        // output will be NaN
         result = Math.Sin(negativeInfinity);
         Console.WriteLine(result);

        // Here argument is positive infinity,
        // output will also be NaN
        result = Math.Sin(positiveInfinity);
        Console.WriteLine(result);

        // Here argument is NaN, output will be NaN
        result = Math.Sin(nan);
        Console.WriteLine(result);
    }
}
```

**Output:**

```cs
NaN
NaN
NaN

```