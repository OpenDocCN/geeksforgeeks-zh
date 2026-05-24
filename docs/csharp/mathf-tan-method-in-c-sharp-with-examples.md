# MathF。C# 中的 Tan()方法及示例

> 原文:[https://www . geesforgeks . org/mathf-tan-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/mathf-tan-method-in-c-sharp-with-examples/)

**MathF。Tan(Single)** 是一个内置的 MathF 类方法，它返回给定浮点值参数(指定角度)的正切值。

> **句法:**公静浮檀(浮 x)；
> 这里，x 是切线返回的角度(以弧度为单位)，该参数的类型为*系统。单身*。

**返回值:**该方法将返回**系统类型的 *x* 的切线。单**。如果 *x* 等于 *NegativeInfinity、PositiveInfinity 或 NaN* ，则该方法返回 *NaN* 。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to illustrate the
// MathF.Tan(Single) Method
using System;

class GFG {

    // Main Method
    public static void Main(String[] args)
    {
        float a = 152f;

        // converting the value to radians
        float b = (a * (MathF.PI)) / 180;

        // using method and displaying result
        Console.WriteLine(MathF.Tan(b));
        a = 105f;

        // converting value to radians
        b = (a * (MathF.PI)) / 180;

        // using method and displaying result
        Console.WriteLine(MathF.Tan(b));
        a = 76F;

        // converting value to radians
        b = (a * (MathF.PI)) / 180;

        // using method and displaying result
        Console.WriteLine(MathF.Tan(b));
    }
}
```

**Output:**

```cs
-0.5317094
-3.732049
4.010781

```

**例 2:** 展示 MathF 的工作原理。谭(单)法当论证是 *NaN 还是无穷大*。

```cs
// C# program to illustrate the
// MathF.Tan(Single) Method
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
        result = MathF.Tan(negativeInfinity);
        Console.WriteLine(result);

        // Here argument is positive infinity,
        // so the output will also be NaN
        result = MathF.Tan(positiveInfinity);
        Console.WriteLine(result);

        // Here the argument is NaN, so 
        // the output will be NaN
        result = MathF.Tan(nan);
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