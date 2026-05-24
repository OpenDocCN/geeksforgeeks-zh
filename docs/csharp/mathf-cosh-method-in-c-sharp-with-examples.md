# MathF。C# 中的 Cosh()方法，带示例

> 原文:[https://www . geesforgeks . org/mathf-cosh-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/mathf-cosh-method-in-c-sharp-with-examples/)

***数学。Cosh(Single)*** 方法是内置的 MathF 类方法，它返回给定单值参数的双曲余弦值。

> **语法:**公共静态 float Cosh(float x)；
> 这里，x 是要返回双曲余弦的数字，这个参数的类型是*系统。单身*。

**返回值:**此方法返回类型为*系统的 x 的双曲余弦。单*。如果 x 等于否定有限性或肯定有限性，则返回肯定有限性。如果 x 等于 NaN，则返回 NaN。
以下程序说明了上述方法的使用:
**例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the
// MathF.Cosh(Single) Method
using System;

class GFG {

    // Main Method
    public static void Main(String[] args)
    {

        float num1 = 60.0f, num2 = 0.0f, num3 = 1.0f;

        // It returns the hyperbolic cosine
        // of specified angle in radian
        float coshvalue = MathF.Cosh(num1);
        Console.WriteLine("The Cosh of num1 = " + coshvalue);

        coshvalue = MathF.Cosh(num2);
        Console.WriteLine("The Cosh of num2 = " + coshvalue);

        coshvalue = MathF.Cosh(num3);
        Console.WriteLine("The Cosh of num3 = " + coshvalue);
    }
}
```

**Output:** 

```cs
The Cosh of num1 = 5.710037E+25
The Cosh of num2 = 1
The Cosh of num3 = 1.543081
```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the
// MathF.Cosh(Single) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        float num1 = (30 * (MathF.PI)) / 180;

        // calling result() method
        result(num1);
        result(Single.NaN);
        result(Single.NegativeInfinity);
        result(Single.PositiveInfinity);
    }

    // defining result() method
    public static void result(float value)
    {

        // using the method
        float result = MathF.Cosh(value);

        // Display the value
        Console.WriteLine("Cosh({0}) will be {1}",
                                value, result);
    }
}
```

**Output:** 

```cs
Cosh(0.5235988) will be 1.140238
Cosh(NaN) will be NaN
Cosh(-Infinity) will be Infinity
Cosh(Infinity) will be Infinity
```