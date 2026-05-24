# MathF。用例子截断 C# 中的()方法

> 原文:[https://www . geesforgeks . org/mathf-truncate-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/mathf-truncate-method-in-c-sharp-with-examples/)

在 C# 中 ***MathF。Truncate(Single)*** 是一种 MathF 类方法，用于计算指定的单个数或单精度浮点数的整数部分。
**语法:**

```cs
public static float Truncate (float x);
```

**参数:**

> **x:** 是要截断的指定数字，该参数的类型为*系统。单*。

**返回类型:**此方法只返回 *x* 的整数部分，丢弃小数部分。这种方法的类型是*系统。单*。
**例:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# Program to illustrate the
// MathF.Truncate(Single) Method
using System;

class Geeks {

    // Main Method
    public static void Main()
    {

        // variables of float type
        float x1 = 7845.56478452f;
        float x2 = 12548.3242f;

        // using method and displaying result
        Console.WriteLine(MathF.Truncate(x1));
        Console.WriteLine(MathF.Truncate(x2));
    }
}
```

**Output:** 

```cs
7845
12548
```