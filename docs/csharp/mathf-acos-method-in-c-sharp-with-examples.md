# MathF。C# 中的 Acos()方法及示例

> 原文:[https://www . geesforgeks . org/mathf-acos-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/mathf-acos-method-in-c-sharp-with-examples/)

**MathF。Acos(Single)** 方法用于返回余弦值作为单个或浮点值参数给出的角度。如果参数是 NaN，那么结果就是 NaN。

> **语法:**公共静态 float Acos(float x)；
> 这里，它取一个标准的浮点数。
> 
> **返回值:**该方法返回一个角度θ，以弧度为单位，类型为*系统。单*且数值会小于*单。最大值*。

以下程序将说明上述方法的使用:

**例 1:**

```cs
// C# program to demonstrate the
// MathF.Acos(Single) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declaring and initializing value
        float value = 0.5f;

        // getting absolute angle value in float
        // using Acos() method
        float result = MathF.Acos(value);

        // Display the value
        Console.WriteLine("Angle is {0}", result);
    }
}
```

**Output:**

```cs
Angle is 1.047198

```

**例 2:**

```cs
// C# program to demonstrate the
// MathF.Acos(Single) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // calling get() method
        get(0.19f);
        get(Single.NaN);
        get(Single.NegativeInfinity);
        get(Single.PositiveInfinity);
    }

    // defining get() method
    public static void get(float value)
    {

        // getting absolute angle value in float
        // using Acos() method
        float result = MathF.Acos(value);

        // Display the value
        Console.WriteLine("Acos({0}) will be {1}",
                                   value, result);
    }
}
```

**Output:**

```cs
Acos(0.19) will be 1.379634
Acos(NaN) will be NaN
Acos(-Infinity) will be NaN
Acos(Infinity) will be NaN

```