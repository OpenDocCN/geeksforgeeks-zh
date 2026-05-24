# MathF.Atan(Single) 方法

> 原文: [https://www.geeksforgeeks.org/mathf-atan-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/mathf-atan-method-in-c-sharp-with-examples/)

`MathF.Atan(Single)` 方法用于返回其正切值为指定单精度浮点数参数的角度。如果参数是 `NaN`，那么结果就是 `NaN`。

## 语法

```cs
public static float Atan(float x);
```

这里，它取一个标准的浮点数 `x`。

## 返回值

该方法返回一个角度 `θ`，以弧度为单位，类型为 `System.Single`，其值将小于 `Single.MaxValue`。

## 示例 1

```cs
// C# program to demonstrate the
// MathF.Atan(Single) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing value
        float value = 0.5f;

        // getting absolute angle value in float
        // using Atan() method
        float round = MathF.Atan(value);

        // Display the value
        Console.WriteLine("Angle is {0}", round);
    }
}
```

**输出：**

```cs
Angle is 0.4636476
```

## 示例 2

```cs
// C# program to demonstrate the
// MathF.Atan(Single) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // calling get() method
        Console.WriteLine("Angle(in radian) are respectively");
        get(0.19f);
        get(0.23f);
        get(0.45f);
        get(0.67f);
    }

    // defining get() method
    public static void get(float value)
    {
        // getting absolute angle value in float
        // using Atan() method
        float round = MathF.Atan(value);

        // Display the value
        Console.WriteLine("Angle of Atan({0}) will be {1}",
                         value, round);
    }
}
```

**输出：**

```cs
Angle(in radian) are respectively
Angle of Atan(0.19) will be 0.1877619
Angle of Atan(0.23) will be 0.2260684
Angle of Atan(0.45) will be 0.4228539
Angle of Atan(0.67) will be 0.5903068
```