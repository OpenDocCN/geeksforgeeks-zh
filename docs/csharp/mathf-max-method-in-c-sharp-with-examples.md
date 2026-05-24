# MathF。C# 中的 Max()方法，示例

> 原文:[https://www . geesforgeks . org/mathf-max-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/mathf-max-method-in-c-sharp-with-examples/)

在 C# 中， ***Max(Single，Single)*** 是一个 MathF 类方法，用于返回两个指定数字中较大的一个。

> **语法:**公共静态 float Max (float x，float y)；
> 这里，x 和 y 是比较的两个浮点数。
> 
> **返回类型:**该方法返回参数列表中指定的两个数字的最大值，返回类型取决于传递的参数类型。

**示例:**

```cs
// C# program to demonstrate the
// MathF.Max(Single, Single) method
using System;

class GFG {

    // Main Method
    static void Main()
    {
        // taking different float values
        float f1 = 34.56f, f2 = 37.3412f;
        float f3 = -675.2f, f4 = -56.47f;

        // displaying result
        Console.WriteLine(MathF.Max(f1, f2));
        Console.WriteLine(MathF.Max(f3, f4));
    }
}
```

**Output:**

```cs
37.3412
-56.47

```