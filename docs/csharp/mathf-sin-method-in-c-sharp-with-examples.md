# MathF。C# 中的 Sin()方法，带示例

> 原文:[https://www . geesforgeks . org/mathf-sin-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/mathf-sin-method-in-c-sharp-with-examples/)

**MathF。Sin(Single)** 是一个内置的 MathF 类方法，它返回给定浮点值参数(指定角度)的正弦值。

> **语法:**公共静态 float Sin(float x)；
> 这里，x 是要返回正弦的角度(以弧度为单位)，该参数的类型为*系统。单身*。

**返回值:**该方法将返回**系统类型的 *x* 的正弦值。单**。如果 *x* 等于 *NegativeInfinity、PositiveInfinity 或 NaN* ，则该方法返回 *NaN* 。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to illustrate the
// MathF.Sin(Single) Method
using System;

class GFG {

    // Main Method
    public static void Main(String[] args)
    {
        float a = 17f;

        // converting value to radians
        float b = (a * (MathF.PI)) / 180;

        // using method and displaying result
        Console.WriteLine(MathF.Sin(b));
        a = 47f;

        // converting value to radians
        b = (a * (MathF.PI)) / 180;

        // using method and displaying result
        Console.WriteLine(MathF.Sin(b));
        a = 96F;

        // converting value to radians
        b = (a * (MathF.PI)) / 180;

        // using method and displaying result
        Console.WriteLine(MathF.Sin(b));
    }
}
```

**Output:**

```cs
0.2923717
0.7313538
0.9945219

```

**例 2:** 展示 MathF 的工作原理。Sin(Single)方法当自变量是 *NaN 或无穷大*时。

```cs
// C# program to illustrate the
// MathF.Sin(Single) Method
using System;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Taking the positive, negative
        // infinity and NaN
        float positiveInfinity = float.PositiveInfinity;
        float negativeInfinity = float.NegativeInfinity;
        float nan = float.NaN;

        float result;

        // Here argument is negative infinity,
        // so the output will be NaN
        result = MathF.Sin(negativeInfinity);
        Console.WriteLine(result);

        // Here argument is positive infinity,
        // so the output will also be NaN
        result = MathF.Sin(positiveInfinity);
        Console.WriteLine(result);

        // Here the argument is NaN, so 
        // the output will be NaN
        result = MathF.Sin(nan);
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