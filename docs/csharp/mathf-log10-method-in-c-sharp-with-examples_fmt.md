# MathF.Log10() 方法及示例（C#）

> 原文：[https://www.geeksforgeeks.org/mathf-log10-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/mathf-log10-method-in-c-sharp-with-examples/)

## 方法介绍

在 C# 中，`MathF.Log10(Single)` 是一个 `MathF` 类方法。它用于返回指定数字的以 10 为底的对数。

## 语法

```cs
public static float Log10(float x);
```

这里，`x` 是指定的要计算对数的数字，类型为 `System.Single`。

## 返回值

返回 `x` 的对数（以 10 为底），类型为 `System.Single`。

## 注意事项

参数 `x` 始终指定为 10 进制数。返回值取决于传递的参数。以下是一些情况：

*   如果参数为正数，则方法将返回常用对数或 `log10(val)`。
*   如果参数是零，那么结果就是负无穷大。
*   如果参数为负数（小于零）或等于 `NaN`，则结果为 `NaN`。
*   如果参数是正无穷大，那么结果就是正无穷大。
*   如果参数是负无穷大，那么结果就是 `NaN`。

## 示例

```cs
// C# program to demonstrate working
// of MathF.Log10(Single) method
using System;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {
        // float values whose logarithm
        // to be calculated
        float a = 9.887f;
        float b = 0f;
        float c = -4.45f;
        float nan = Single.NaN;
        float positiveInfinity = Single.PositiveInfinity;
        float negativeInfinity = Single.NegativeInfinity;

        // Input is positive number so output
        // will be logarithm of number
        Console.WriteLine(MathF.Log10(a));

        // positive zero as argument, so output
        // will be -Infinity
        Console.WriteLine(MathF.Log10(b));

        // Input is negative number so output
        // will be NaN
        Console.WriteLine(MathF.Log10(c));

        // Input is NaN so output
        // will be NaN
        Console.WriteLine(MathF.Log10(nan));

        // Input is PositiveInfinity so output
        // will be Infinity
        Console.WriteLine(MathF.Log10(positiveInfinity));

        // Input is NegativeInfinity so output
        // will be NaN
        Console.WriteLine(MathF.Log10(negativeInfinity));
    }
}
```

## 输出

```cs
0.9950646
-Infinity
NaN
NaN
Infinity
NaN
```