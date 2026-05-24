# MathF。C# 中的 Sinh()方法，带示例

> 原文:[https://www . geesforgeks . org/mathf-sinh-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/mathf-sinh-method-in-c-sharp-with-examples/)

***数学。Sinh(Single)*** 方法是内置的 MathF 类方法，它返回给定单值参数的双曲正弦值。

> **语法:**公共静态 float Sinh(float x)；
> 这里，x 是要返回双曲正弦的数字，这个参数的类型是*系统。单身*。

**返回值:**此方法返回类型为*系统的 x 的双曲正弦值。单*。如果 x 等于否定有限性或肯定有限性，则返回肯定有限性。如果 x 等于 NaN，则返回 NaN。
以下程序说明了上述方法的使用:
**例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the
// MathF.Sinh(Single) Method
using System;

class GFG {

    // Main Method
    public static void Main(String[] args)
    {

        float num1 = 45.0f, num2 = 0.0f, num3 = 1.0f;

        // It returns the hyperbolic sine of
        // specified angle in radian
        float sinhvalue = MathF.Sinh(num1);
        Console.WriteLine("The Sinh of num1 = " + sinhvalue);

        sinhvalue = MathF.Sinh(num2);
        Console.WriteLine("The Sinh of num2 = " + sinhvalue);

        sinhvalue = MathF.Sinh(num3);
        Console.WriteLine("The Sinh of num3 = " + sinhvalue);
    }
}
```

**Output:** 

```cs
The Sinh of num1 = 1.746714E+19
The Sinh of num2 = 0
The Sinh of num3 = 1.175201
```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the
// MathF.Sinh(Single) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        float num1 = (60 * (MathF.PI)) / 180;

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
        float result = MathF.Sinh(value);

        // Display the value
        Console.WriteLine("Sinh({0}) will be {1}",
                                value, result);
    }
}
```

**Output:** 

```cs
Sinh(1.047198) will be 1.249367
Sinh(NaN) will be NaN
Sinh(-Infinity) will be -Infinity
Sinh(Infinity) will be Infinity
```