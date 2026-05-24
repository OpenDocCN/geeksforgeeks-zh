# C# |数学。谭()法

> 原文:[https://www.geeksforgeeks.org/c-sharp-math-tan-method/](https://www.geeksforgeeks.org/c-sharp-math-tan-method/)

***数学。Tan()*** 是一个内置的数学类方法，它返回给定双值参数(指定角度)的正切值。

**语法:**

```cs
public static double Tan(double num)
```

**参数:**

> **num:** 是返回切线的角度(以弧度为单位)，该参数的类型为*系统。双*。

**返回值:**返回类型为**系统的数值的正切值。双**。如果 num 等于*否定有限性、肯定有限性或 NaN* ，则该方法返回 *NaN* 。

下面是说明数学的程序。谭()法。

**程序 1:** 展示数学的工作原理。谭()法。

```cs
// C# program to demonstrate working
// Math.Tan() method
using System;

class Geeks {

    // Main Method
    public static void Main(String []args)
    {
        double a = 12;

        // converting value to radians
        double b = (a * (Math.PI)) / 180;

        // using method and displaying result
        Console.WriteLine(Math.Tan(b));
        a = 63;

        // converting value to radians
        b = (a * (Math.PI)) / 180;

        // using method and displaying result
        Console.WriteLine(Math.Tan(b));
        a = 187;

        // converting value to radians
        b = (a * (Math.PI)) / 180;

        // using method and displaying result
        Console.WriteLine(Math.Tan(b));
        a = 45;

        // converting value to radians
        b = (a * (Math.PI)) / 180;

        // using method and displaying result
        Console.WriteLine(Math.Tan(b));
    }
}
```

**Output:**

```cs
0.212556561670022
1.96261050550515
0.122784560902905
1

```

**节目 2:** 展示数学作品。谭()法时的论点是 *NaN 或无穷大】。*

```cs
// C# program to demonstrate working
// Math.Tan() method in infinity case
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
         result = Math.Tan(negativeInfinity);
         Console.WriteLine(result);

        // Here argument is positive infinity,
        // output will also be NaN
        result = Math.Tan(positiveInfinity);
        Console.WriteLine(result);

        // Here argument is NaN, output will be NaN
        result = Math.Tan(nan);
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