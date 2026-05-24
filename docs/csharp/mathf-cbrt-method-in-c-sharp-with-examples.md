# MathF。C# 中的 Cbrt()方法，带示例

> 原文:[https://www . geesforgeks . org/mathf-cbrt-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/mathf-cbrt-method-in-c-sharp-with-examples/)

**MathF。Cbrt(Single)** 方法用于返回浮点值的立方根。

> **语法:**公共静态 float Cbort(float x)；
> 这里，它取一个标准的浮点数。
> 
> **返回值:**该方法返回给定值的立方根。

**例 1:**

```cs
// C# program to demonstrate the
// MathF.Cbrt(Single) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declaring and initializing value
        float value = 27f;

        // getting cube root of value
        // using Cbrt() method
        float round = MathF.Cbrt(value);

        // Display the value
        Console.WriteLine("Cube root of {0} is {1}",
                                     value, round);
    }
}
```

**Output:**

```cs
Cube root of 27 is 3

```

**例 2:**

```cs
// C# program to demonstrate the
// MathF.Cbrt(Single) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // calling get() method
        Console.WriteLine("Cube root of given "+
                    "numbers are respectively");
        get(8f);
        get(27.8967f);
        get(64f);
        get(125.2534f);
    }

    // defining get() method
    public static void get(float value)
    {

        // getting cube root of given value
        // using Cbrt() method
        float round = MathF.Cbrt(value);

        // Display the value
        Console.WriteLine("Cube root of {0} is {1}",
                                    value, round);
    }
}
```

**Output:**

```cs
Cube root of given numbers are respectively
Cube root of 8 is 2
Cube root of 27.8967 is 3.03285
Cube root of 64 is 4
Cube root of 125.2534 is 5.003376

```