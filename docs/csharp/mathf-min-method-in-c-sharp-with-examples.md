# MathF。C# 中的 Min()方法，示例

> 原文:[https://www . geesforgeks . org/mathf-min-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/mathf-min-method-in-c-sharp-with-examples/)

在 C# 中， ***Min(Single，Single)*** 是一个 MathF 类方法，用于返回两个指定数字的最小值。

> **语法:**公共静态 float Min (float x，float y)；
> 这里，x 和 y 是比较的两个浮点数。

**返回类型:**该方法返回参数列表中指定的两个数字的最小值，返回类型取决于传递的参数类型。

**示例:**

```cs
// C# program to demonstrate the
// MathF.Min(Single, Single) method
using System;

class GFG {

    // Main Method
    static void Main()
    {
        // taking different float values
        float f1 = 56.48f, f2 = 78.123457f;
        float f3 = -785.2f, f4 = -58.2547f;

        // displaying result
        Console.WriteLine(MathF.Min(f1, f2));
        Console.WriteLine(MathF.Min(f3, f4));
    }
}
```

**Output:**

```cs
56.48
-785.2

```