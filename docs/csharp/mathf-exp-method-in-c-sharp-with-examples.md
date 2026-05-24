# MathF。C# 中的 Exp()方法，带示例

> 原文:[https://www . geesforgeks . org/mathf-exp-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/mathf-exp-method-in-c-sharp-with-examples/)

在 C# 中， ***Exp(Single)*** 是一个 MathF 类方法，用于将 **e** 提升到指定的幂。这里 *e* 是一个数学常数，其值约为 **2.71828** 。

> **语法:**公共静态浮点 Exp(float x)；
> 此处， **x** 为*系统类型所需编号。单*指定一个功率。
> 
> **返回类型:**返回一个数字 *e* 升到 *x* 类型*系统的幂。单*。

**注:**

*   如果 *x* 等于 *NaN* ，则返回值为 *NaN* 。
*   如果 *x* 等于*正定性*，则返回值为*无穷大*。
*   如果 *x* 等于*负有限*，则返回值为 *0* 。

**例 1:**

```cs
// C# Program to illustrate the
// MathF.Exp(Single) Method
using System;

class Geeks {

    // Main Method
    public static void Main()
    {

        // using the method
        Console.WriteLine(MathF.Exp(7.0f));
        Console.WriteLine(MathF.Exp(458.95f));
        Console.WriteLine(MathF.Exp(9.487f));
        Console.WriteLine(MathF.Exp(0.00f));
    }
}
```

**Output:**

```cs
1096.633
Infinity
13187.18
1

```

**例 2:**

```cs
// C# Program to illustrate the
// MathF.Exp(Single) Method by
// taking NaN, PositiveInfinity
// and NegativeInfinity]
using System;

class Geeks {

    // Main Method
    public static void Main()
    {

        // Taking NaN
        Console.WriteLine(MathF.Exp(Single.NaN));

        // Taking PositiveInfinity
        Console.WriteLine(MathF.Exp(Single.PositiveInfinity));

        // Taking NegativeInfinity
        Console.WriteLine(MathF.Exp(Single.NegativeInfinity));
    }
}
```

**Output:**

```cs
NaN
Infinity
0

```