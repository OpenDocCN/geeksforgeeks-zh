# C# 中的 Math.Log10() 方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-math-log10-method/](https://www.geeksforgeeks.org/c-sharp-math-log10-method/)

在 C# 中，`Math.Log10()` 是 `Math` 类的一个方法。它用于返回指定数字的以 10 为底的对数。

**语法：**

```cs
public static double Log10(double val)
```

**参数：**

> `val`：要计算对数的指定数字，类型为 `System.Double`。

**返回值：** 返回 `val` 的对数（以 10 为底），类型为 `System.Double`。

**注意：** 参数 `val` 始终作为以 10 为底的对数的真数。返回值取决于传递的参数。以下是一些情况：

*   如果参数是正数（`+`），则该方法将返回以 10 为底的对数，即 `log10(val)`。
*   如果参数是零（`0`），结果是负无穷大（`-Infinity`）。
*   如果参数是负数（小于零）或等于 `NaN`，结果是 `NaN`。
*   如果参数是正无穷大（`PositiveInfinity`），结果是 `NaN`。
*   如果参数是负无穷大（`NegativeInfinity`），结果是 `NaN`。

**示例：**

```cs
// C# program to demonstrate working
// of Math.Log10(Double) method
using System;

class Geeks {

// Main Method
    public static void Main(String[] args)
    {

// double values whose logarithm 
        // to be calculated
        double a = 4.55;
        double b = 0;
        double c = -2.45;
        double nan = Double.NaN;
        double positiveInfinity = Double.PositiveInfinity;     
        double negativeInfinity = Double.NegativeInfinity;

// Input is positive number so output
        // will be logarithm of number
        Console.WriteLine(Math.Log10(a));

// positive zero as argument, so output 
        // will be -Infinity
        Console.WriteLine(Math.Log10(b));

// Input is negative number so output
        // will be NaN
        Console.WriteLine(Math.Log10(c));

// Input is NaN so output
        // will be NaN
        Console.WriteLine(Math.Log10(nan));

// Input is PositiveInfinity so output
        // will be Infinity
        Console.WriteLine(Math.Log10(positiveInfinity));

// Input is NegativeInfinity so output
        // will be NaN
        Console.WriteLine(Math.Log10(negativeInfinity));
    }
}
```

**输出：**

```cs
0.658011396657112
-Infinity
NaN
NaN
Infinity
NaN
```

**参考：** [https://msdn.microsoft.com/en-us/library/system.math.log10(v=vs.110).aspx](https://msdn.microsoft.com/en-us/library/system.math.log10(v=vs.110).aspx)