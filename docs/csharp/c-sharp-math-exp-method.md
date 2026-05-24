# C# |数学。Exp()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-math-exp-method/](https://www.geeksforgeeks.org/c-sharp-math-exp-method/)

在 C# 中， ***Exp()*** 是一个数学类方法，用于将 **e** 提升到指定的幂。这里 *e* 是一个数学常数，其值约为 **2.71828** 。 **Exp()** 是 *[Log()](https://www.geeksforgeeks.org/c-math-log-method/)* 的逆。

**语法:**

```cs
public static double Exp (double num);
```

**参数:**

> **编号:**为*系统所需型号。双*指定一个功率。

**返回类型:**返回一个数字 *e* 加到类型*系统的 *num* 上。双*。

**注:**

*   If *num* is equal to *nan* , the return value is *nan* .
*   If *number* is equal to *positive value* , the return value is *infinity* .
*   If *value* is equal to *negative value* , the return value is *0* .

**例 1:**

```cs
// C# Program to illustrate the
// Math.Exp(Double) Method
using System;

class Geeks {

    // Main Method
    public static void Main()
    {

        // using the method
        Console.WriteLine(Math.Exp(10.0));
        Console.WriteLine(Math.Exp(15.57));
        Console.WriteLine(Math.Exp(529.548));
        Console.WriteLine(Math.Exp(0.00));
    }
}
```

**输出:**

```cs
22026.4657948067
5780495.71030692
9.54496417945595E+229
1

```

**例 2:**

```cs
// C# Program to illustrate the
// Math.Exp(Double) Method by 
// taking NaN, PositiveInfinity
// and NegativeInfinity]
using System;

class Geeks {

    // Main Method
    public static void Main()
    {

        // Taking NaN
        Console.WriteLine(Math.Exp(Double.NaN));

        // Taking PositiveInfinity
        Console.WriteLine(Math.Exp(Double.PositiveInfinity));

        // Taking NegativeInfinity
        Console.WriteLine(Math.Exp(Double.NegativeInfinity));
    }
}
```

**输出:**

```cs
NaN
Infinity
0

```

**参考:**T2？view=netcore-2.1