# MathF。C# 中的 Abs()方法，示例

> 原文:[https://www . geesforgeks . org/mathf-ABS-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/mathf-abs-method-in-c-sharp-with-examples/)

**MathF。Abs(Single)** 方法用于返回指定浮点数的绝对值。

> **语法:**公共静态 float Abs(float x)；
> 这里，它取一个标准的浮点数。
> 
> **返回值:**该方法返回小于 **Single.MaxValue.** 的浮点值

**例 1:**

```cs
// C# program to demonstrate the
// MathF.Abs(Single)  Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declaring and initializing value
        float value = 4.5f;

        // Getting absolute float
        // using Abs() method
        float round = MathF.Abs(value);

        // Display the value
        Console.WriteLine("Absolute float value is {0}",
                                                 round);
    }
}
```

**Output:**

```cs
Absolute float value is 4.5

```

**例 2:**

```cs
// C# program to demonstrate the
// MathF.Abs(Single) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // calling get() method
        get(20f);
        get(30.5f);
        get(40.5f);
        get(4294.586f);
    }

    // defining get() method
    public static void get(float value)
    {

        // getting absolute float
        // using Abs() method
        float round = MathF.Abs(value);

        // Display the value
        Console.WriteLine("Float value is {0}", round);
    }
}
```

**Output:**

```cs
Float value is 20
Float value is 30.5
Float value is 40.5
Float value is 4294.586

```