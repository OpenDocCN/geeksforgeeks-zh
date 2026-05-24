# MathF。C# 中的 Asinh()方法，带示例

> 原文:[https://www . geesforgeks . org/mathf-asinh-method-in-c-with-examples/](https://www.geeksforgeeks.org/mathf-asinh-method-in-c-with-examples/)

**MathF。Asinh(Single)** 方法用于返回浮点值的双曲反正弦。

> **语法:**公共静态 float Asinh(float x)；
> 这里，它取一个标准的浮点数。
> 
> **返回值:**该方法返回给定值的双曲反正弦。如果该数字小于 1，则返回 NaN。

以下是说明上述方法使用的程序:

**例 1:**

```cs
// C# program to demonstrate the
// MathF.Asinh(Single) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declaring and initializing value
        float value = 1.5f;

        // getting hyperbolic arc-cosine value
        // using Asinh() method
        float result = MathF.Asinh(value);

        // Display the value
        Console.WriteLine("Angle is {0}", result);
    }
}
```

**Output:**

```cs
Angle is 1.194763

```

**例 2:**

```cs
// C# program to demonstrate the
// MathF.Asinh(Single) Method
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
        // using Asinh() method
        float result = MathF.Asinh(value);

        // Display the value
        Console.WriteLine("Angle is {0}", result);
    }
}
```

**Output:**

```cs
Angle is 0.188875
Angle is NaN
Angle is -Infinity
Angle is Infinity

```