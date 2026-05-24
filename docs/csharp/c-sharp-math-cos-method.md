# C# |数学。Cos()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-math-cos-method/](https://www.geeksforgeeks.org/c-sharp-math-cos-method/)

**数学。Cos()** 是一个内置的数学类方法，它返回给定双值参数(指定角度)的余弦值。

**语法:**

```cs
public static double Cos(double num)
```

**参数:**

> **num:** 是返回余弦的角度(以弧度为单位)，该参数的类型为*系统。双*。

**返回值:**返回类型为**系统的数的值。双**。如果 num 等于*否定有限性、肯定有限性或 NaN* ，则该方法返回 *NaN* 。

下面是说明数学的程序。Cos()方法。

**程序 1:** 展示数学的工作原理。Cos()方法。

```cs
// C# program to demonstrate working
// Math.Cos() method
using System;

class Geeks {

    // Main Method
    public static void Main(String []args)
    {
        double a = 70;

        // converting value to radians
        double b = (a * (Math.PI)) / 180;

        // using method and displaying result
        Console.WriteLine(Math.Cos(b));
        a = 50;

        // converting value to radians
        b = (a * (Math.PI)) / 180;

        // using method and displaying result
        Console.WriteLine(Math.Cos(b));
        a = 73;

        // converting value to radians
        b = (a * (Math.PI)) / 180;

        // using method and displaying result
        Console.WriteLine(Math.Cos(b));
        a = 77;

        // converting value to radians
        b = (a * (Math.PI)) / 180;

        // using method and displaying result
        Console.WriteLine(Math.Cos(b));
    }
}
```

**Output:**

```cs
0.342020143325669
0.642787609686539
0.292371704722737
0.224951054343865

```

**程序 2:** 展示数学的工作原理。Cos()方法时的自变量是 *NaN 或无穷大*。

```cs
// C# program to demonstrate working
// Math.Cos() method in infinity case
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
         result = Math.Cos(negativeInfinity);
         Console.WriteLine(result);

        // Here argument is positive infinity,
        // output will also be NaN
        result = Math.Cos(positiveInfinity);
        Console.WriteLine(result);

        // Here argument is NaN, output will be NaN
        result = Math.Cos(nan);
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