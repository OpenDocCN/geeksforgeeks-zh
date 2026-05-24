## C# | `Math.Exp()` 方法

> 原文: [https://www.geeksforgeeks.org/c-sharp-math-exp-method/](https://www.geeksforgeeks.org/c-sharp-math-exp-method/)

在 C# 中，`Exp()` 是一个 `Math` 类方法，用于将 **e** 提升到指定的幂。这里 *e* 是一个数学常数，其值约为 **2.71828**。`Exp()` 是 `Log()` 的逆。

**语法:**

```cs
public static double Exp (double num);
```

**参数:**

> **num**: 一个 `System.Double`，用于指定幂。

**返回类型:** 返回一个数字 *e* 加到类型 `System.Double` 的 *num* 上。

**注意:**

*   如果 *num* 等于 `Double.NaN`，则返回值是 `Double.NaN`。
*   如果 *num* 等于 `Double.PositiveInfinity`，则返回值是 `Double.PositiveInfinity`。
*   如果 *num* 等于 `Double.NegativeInfinity`，则返回值是 `0.0`。

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
// and NegativeInfinity
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

**参考:** [https://docs.microsoft.com/en-us/dotnet/api/system.math.exp?view=netcore-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.math.exp?view=netcore-2.1)