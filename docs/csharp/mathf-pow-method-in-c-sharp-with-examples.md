# MathF。C# 中的 Pow()方法，带示例

> 原文:[https://www . geesforgeks . org/mathf-pow-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/mathf-pow-method-in-c-sharp-with-examples/)

在 C# 中 ***MathF。***pow(Single，Single)是一个 MathF 类方法。这种方法用来计算一个数与另一个数的幂的乘积。

> **语法:**公共静态 float Pow (float x，float y)；
> 
> **参数:**
> **x:** 是一个要加幂的单精度浮点数，这个参数的类型是 *System。单*。
> **y:** 是单精度浮点数，指定幂或指数，该参数的类型为 *System。单*。

**返回类型:**函数返回升到幂的基数。这种方法的返回类型是*系统。单*

**示例:**

```cs
// C# program to illustrate the
// MathF.Pow(Single, Single) Method
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // Find power using MathF.Pow
        // 8 is base and 4 is power or
        // index or exponent of a number
        float pow_ab = MathF.Pow(8f, 4f);

        // Print the result
        Console.WriteLine(pow_ab);

        // 7.5 is base and 2 is power or
        // index or exponent of a number
        float pow_tt = MathF.Pow(7.5f, 2f);

        // Print the result
        Console.WriteLine(pow_tt);

        // 1234 is base and 7 is power or
        // index or exponent of a number
        float pow_t = MathF.Pow(1234f, 7f);

        // Print the result
        Console.WriteLine(pow_t);
    }
}
```

**Output:**

```cs
4096
56.25
4.357186E+21

```