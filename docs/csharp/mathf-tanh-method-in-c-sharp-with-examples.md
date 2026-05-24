# MathF。C# 中的 Tanh()方法，带示例

> 原文:[https://www . geesforgeks . org/mathf-tanh-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/mathf-tanh-method-in-c-sharp-with-examples/)

***数学。Tanh(Single)*** 方法是内置的 MathF 类方法，它返回给定单值参数的双曲正切值。

> **语法:**公共静态 float Tanh(float x)；
> 这里，x 是要返回双曲正切的数字，这个参数的类型是*系统。单身*。

**返回值:**此方法返回类型为*系统的 x 的双曲正切值。单*。如果 x 等于否定有限性或肯定有限性，则返回肯定有限性。如果 x 等于 NaN，则返回 NaN。
以下程序说明了上述方法的使用:
**例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the
// MathF.Tanh(Single) Method
using System;

class GFG {

    // Main Method
    public static void Main(String[] args)
    {

        float num1 = 70.0f, num2 = 0.0f, num3 = 1.0f;

        // It returns the hyperbolic tangent
        // of specified angle in radian
        float tanhvalue = MathF.Tanh(num1);
        Console.WriteLine("The Tanh of num1 = " + tanhvalue);

        tanhvalue = MathF.Tanh(num2);
        Console.WriteLine("The Tanh of num2 = " + tanhvalue);

        tanhvalue = MathF.Tanh(num3);
        Console.WriteLine("The Tanh of num3 = " + tanhvalue);
    }
}
```

**Output:** 

```cs
The Tanh of num1 = 1
The Tanh of num2 = 0
The Tanh of num3 = 0.7615942
```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the
// MathF.Tanh(Single) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        float num1 = (90 * (MathF.PI)) / 180;

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
        float result = MathF.Tanh(value);

        // Display the value
        Console.WriteLine("Tanh({0}) will be {1}",
                                   value, result);
    }
}
```

**Output:** 

```cs
Tanh(1.570796) will be 0.9171523
Tanh(NaN) will be NaN
Tanh(-Infinity) will be -1
Tanh(Infinity) will be 1
```