# MathF.Cos(Single) 方法

> 原文：[https://www.geeksforgeeks.org/mathf-cos-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/mathf-cos-method-in-c-sharp-with-examples/)

## 方法介绍

`MathF.Cos(Single)` 是一个内置的 `MathF` 类方法，它返回给定浮点值参数（指定角度）的余弦值。

## 语法

```cs
public static float Cos(float x);
```

这里，`x` 是返回余弦的角度（以弧度为单位），该参数的类型为 `System.Single`。

## 返回值

该方法将返回 `x` 的余弦，类型为 `System.Single`。如果 `x` 等于 `NegativeInfinity`、`PositiveInfinity` 或 `NaN`，则该方法返回 `NaN`。

## 示例

以下是说明上述方法使用的程序：

### 例 1

```cs
// C# program to illustrate the
// MathF.Cos(Single) Method
using System;

class GFG{

// Main Method
    public static void Main(String[] args)
    {
        float a = 45f;

// converting value to radians
        float b = (a * (MathF.PI)) / 180;

// using method and displaying result
        Console.WriteLine(MathF.Cos(b));

        a = 54f;

// converting value to radians
        b = (a * (MathF.PI)) / 180;

// using method and displaying result
        Console.WriteLine(MathF.Cos(b));

        a = 70f;

// converting value to radians
        b = (a * (MathF.PI)) / 180;

// using method and displaying result
        Console.WriteLine(MathF.Cos(b));
    }
}
```

**Output:**

```cs
0.7071068
0.5877852
0.34202
```

### 例 2

展示 `MathF.Cos(Single)` 方法在参数为 `NaN` 或无穷大时的工作原理。

```cs
// C# program to illustrate the
// MathF.Cos(Single) method
using System;

class GFG {

// Main Method
    public static void Main(String[] args)
    {

// taking infinity values
        float positiveInfinity = float.PositiveInfinity;
        float negativeInfinity = float.NegativeInfinity;

// taking NaN
        float nan = float.NaN;

        float result;

// Here argument is negative infinity,
        // so the output will be NaN
        result = MathF.Cos(negativeInfinity);
        Console.WriteLine(result);

// Here argument is positive infinity,
        // so the output will also be NaN
        result = MathF.Cos(positiveInfinity);
        Console.WriteLine(result);

// Here argument is NaN, output will be NaN
        result = MathF.Cos(nan);
        Console.WriteLine(result);
    }
}
```

**Output:**

```cs
NaN
NaN
NaN
```