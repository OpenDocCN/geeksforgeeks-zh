# MathF。C# 中的 Floor()方法，示例

> 原文:[https://www . geesforgeks . org/mathf-floor-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/mathf-floor-method-in-c-sharp-with-examples/)

在 C# 中 ***MathF。*楼(单)**是一个 MathF 类的方法。此方法用于查找*最大整数*，该整数小于或等于参数列表中指定的浮点值。

> **语法:**公共静态 Floor Floor(float x)；
> 这里，x 是必须计算其最低值的浮动(单一)值。
> 
> **返回类型:**该方法返回的最大整数值将小于或等于 *x* 。

**示例:**

```cs
// C# program to illustrate the
// MathF.Floor(Single) Method
using System;

class GFG {

    // Main method
    static void Main()
    {

        // taking float values
        float x1 = 37.00f;
        float x2 = 99.99f;
        float x3 = 0.2154f; 
        float x4 = 123.123f; 
        float x5 = -2.2f; 
        float x6 = -123.123f; 

        // calling the method
        result(x1);
        result(x2);
        result(x3);
        result(x4);
        result(x5);
        result(x6);
    }

     public static void result(float t1)
     {
        // Print the original values
        // and Floor values
        Console.WriteLine("Input Value = " + t1);

        // using the MathF.Floor() Method
        Console.WriteLine("Floor value = " + MathF.Floor(t1));
     }
}
```

**Output:**

```cs
Input Value = 37
Floor value = 37
Input Value = 99.99
Floor value = 99
Input Value = 0.2154
Floor value = 0
Input Value = 123.123
Floor value = 123
Input Value = -2.2
Floor value = -3
Input Value = -123.123
Floor value = -124

```