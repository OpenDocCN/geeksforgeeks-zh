# MathF。C# 中的 Atanh()方法，带示例

> 原文:[https://www . geesforgeks . org/mathf-atanh-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/mathf-atanh-method-in-c-sharp-with-examples/)

**MathF。方法用于返回浮点值的双曲反正切。**

> **语法:**公共静态 float Atanh(float x)；
> 这里，它取一个标准的浮点数。
> 
> **返回值:**此方法返回给定值的双曲反正切。如果该数字小于 1，则返回 NaN。

以下是说明上述方法使用的程序:

**例 1:**

```cs
// C# program to demonstrate the
// MathF.Atanh(Single) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declaring and initializing value
        float value = 1.7f;

        // getting hyperbolic arc-tangent value
        // using Atanh() method
        float result = MathF.Atanh(value);

        // Display the value
        Console.WriteLine("Angle is {0}", result);
    }
}
```

**Output:**

```cs
Angle is NaN

```

**例 2:**

```cs
// C# program to demonstrate the
// MathF.Atanh(Single) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // calling get() method
        get(0.25f);
        get(Single.NaN);
        get(Single.NegativeInfinity);
        get(Single.PositiveInfinity);
    }

    // defining get() method
    public static void get(float value)
    {

        // getting hyperbolic arc-tangent value
        // using Atanh() method
        float result = MathF.Atanh(value);

        // Display the value
        Console.WriteLine("Angle is {0}", result);
    }
}
```

**Output:**

```cs
Angle is 0.2554128
Angle is NaN
Angle is NaN
Angle is NaN

```