# MathF。C# 中的天花板()方法，示例

> 原文:[https://www . geesforgeks . org/mathf-天花板-c-in-method-sharp-with-examples/](https://www.geeksforgeeks.org/mathf-ceiling-method-in-c-sharp-with-examples/)

在 C# 中 ***MathF。*上限(单)**是一个 MathF 类的方法。此方法用于查找*最小整数*，该整数大于或等于自变量列表中指定的单值或浮点值。

> **语法:**公共静态浮动天花板(float x)；
> 这里，x 是必须计算其上限值的浮动(单一)值。

**返回类型:**该方法返回大于或等于 *x* 的最小整数值。

**示例:**

```cs
// C# program to illustrate the
// MathF.Ceiling(Single) Method
using System;

class GFG {

    // Main method
    static void Main()
    {

        // taking float values
        float x1 = 33.00f;
        float x2 = 99.99f;

        // Calculate Ceiling values by
        // Using MathF.Ceiling() method
        float r1 = MathF.Ceiling(x1);
        float r2 = MathF.Ceiling(x2);

        // Print the original values
        // and Ceiling values
        Console.WriteLine("Input Value  = " + x1);
        Console.WriteLine("Ceiling value = " + r1);

        // Print the original values
        // and Ceiling values
        Console.WriteLine("Input Value  = " + x2);
        Console.WriteLine("Ceiling value = " + r2);
    }
}
```

**Output:**

```cs
Input Value  = 33
Ceiling value = 33
Input Value  = 99.99
Ceiling value = 100

```