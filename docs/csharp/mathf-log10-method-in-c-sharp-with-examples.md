# MathF。C# 中的 Log10()方法及示例

> 原文:[https://www . geesforgeks . org/mathf-log 10-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/mathf-log10-method-in-c-sharp-with-examples/)

在 C# 中 ***MathF。Log10(Single)*** 是一个 MathF 类方法。它用于返回指定数字的以 10 为底的对数。

**语法:**公共静态 float Log10(float x)；
这里， **x** 是指定的要计算对数的数字，类型为*系统。单*。

**返回值:**返回*值*的对数(以*值*的 10 个对数为基数)，类型为*系统。单*。

**注意:**参数 *x* 始终指定为 10 进制数。返回值取决于传递的参数。以下是一些案例:

*   如果参数为*正*，则方法将返回自然对数或**对数 <sub>10</sub> (val)** 。
*   如果参数是*零*，那么结果就是*否定*。
*   如果参数为*负(小于零)*或等于 *NaN* ，则结果为 *NaN* 。
*   如果参数是*正定性*，那么结果就是*正定性*。
*   如果论证是*否定*，那么结果就是*楠*。

**示例:**

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

**Output:**

```cs
0.9950646
-Infinity
NaN
NaN
Infinity
NaN

```