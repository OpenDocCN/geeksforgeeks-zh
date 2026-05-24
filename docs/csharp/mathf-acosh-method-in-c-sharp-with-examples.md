# MathF。C# 中的 Acosh()方法，带示例

> 原文:[https://www . geesforgeks . org/mathf-acosh-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/mathf-acosh-method-in-c-sharp-with-examples/)

**MathF。方法用于返回浮点值的双曲余弦值。**

> **语法:**公共静态 float Acosh(float x)；
> 这里，它取一个标准的浮点数。
> 
> **返回值:**此方法返回给定值的双曲弧余弦。如果该数字小于 1，则返回 NaN。

以下是说明上述方法使用的程序:

**例 1:**

```cs
// C# program to demonstrate the
// MathF.Acosh(Single) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declaring and initializing value
        float value = 2.5f;

        // getting hyperbolic arc-cosine value
        // using Acosh() method
        float result = MathF.Acosh(value);

        // Display the value
        Console.WriteLine("Angle is {0}", result);
    }
}
```

**Output:**

```cs
Angle is 1.566799

```

**例 2:**

```cs
// C# program to demonstrate the
// MathF.Acosh(Single) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // calling get() method
        get(0.19f);
        get(Single.NaN);
        get(Single.NegativeInfinity);
        get(Single.PositiveInfinity);
    }

    // defining get() method
    public static void get(float value)
    {

        // getting hyperbolic arc-cosine value
        // using Acosh() method
        float result = MathF.Acosh(value);

        // Display the value
        Console.WriteLine("Angle is {0}", result);
    }
}
```

**Output:**

```cs
Angle is NaN
Angle is NaN
Angle is NaN
Angle is Infinity

```