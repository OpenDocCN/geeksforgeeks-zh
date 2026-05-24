# MathF。C# 中的 Asin()方法，带示例

> 原文:[https://www . geesforgeks . org/mathf-asin-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/mathf-asin-method-in-c-sharp-with-examples/)

**MathF。Asin()** 方法用于返回其正弦值作为单个(或浮点)值参数给出的角度。如果参数是 NaN，那么结果就是 NaN。

> **语法:**公共静态 float Asin(float x)；
> 这里，它取一个标准的浮点数。
> 
> **返回值:**该方法返回一个角度θ，以弧度为单位，类型为*系统。单*且数值会小于*单。最大值*。

以下程序将说明上述方法的使用:

**例 1:**

```cs
// C# program to demonstrate the
// MathF.Asin(Single)  Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declaring and initializing value
        float value = 0.7f;

        // getting absolute angle value in float
        // using Asin() method
        float result = MathF.Asin(value);

        // Display the value
        Console.WriteLine("Angle is {0}", result);
    }
}
```

**Output:**

```cs
Angle is 0.7753975

```

**例 2:**

```cs
// C# program to demonstrate the
// MathF.Asin(Single) Method
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
        // using Asin() method
        float result = MathF.Asin(value);

        // Display the value
        Console.WriteLine("Asin({0}) will be {1}",
                                   value, result);
    }
}
```

**Output:**

```cs
Asin(0.19) will be 0.1911621
Asin(NaN) will be NaN
Asin(-Infinity) will be NaN
Asin(Infinity) will be NaN

```