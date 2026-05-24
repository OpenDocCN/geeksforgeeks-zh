# C# Math.Log() 方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-math-log-method/](https://www.geeksforgeeks.org/c-sharp-math-log-method/)

在 C# 中，`Math.Log()` 是 `Math` 类的一个方法。它用于返回指定数字的对数。通过更改传递的参数数量，可以重载此方法。`Math.Log()` 方法的重载列表中总共有 2 种方法，如下所示：

*   `Math.Log(Double)` 方法
*   `Math.Log(Double, Double)` 方法

## Math.Log(Double) 方法

此方法用于返回指定数字的自然对数（以 e 为底）。

**语法：**

```cs
public static double Log(double val)
```

**参数：**

> **val**：是要计算其自然（以 e 为底）对数的指定数，其类型为 `System.Double`。

**返回值：** 返回 `val` 的自然对数，类型为 `System.Double`。

**注意：** 参数 `val` 始终指定为基数 10。返回值取决于传递的参数。以下是一些情况：

*   如果参数为正数，则方法将返回自然对数或 **log<sub>e</sub>(val)**。
*   如果参数是正零，那么结果就是负无穷大（`-Infinity`）。
*   如果参数为负数（小于零）或等于 `NaN`，则结果为 `NaN`。
*   如果参数是正无穷大，那么结果就是正无穷大（`+Infinity`）。
*   如果参数是负无穷大，那么结果就是 `NaN`。

**示例：**

```cs
// C# program to demonstrate working
// of Math.Log(Double) method
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
        Console.WriteLine(Math.Log(a));

        // positive zero as argument, so output 
        // will be -Infinity
        Console.WriteLine(Math.Log(b));

        // Input is negative number so output
        // will be NaN
        Console.WriteLine(Math.Log(c));

        // Input is NaN so output
        // will be NaN
        Console.WriteLine(Math.Log(nan));

        // Input is PositiveInfinity so output
        // will be Infinity
        Console.WriteLine(Math.Log(positiveInfinity));

        // Input is NegativeInfinity so output
        // will be NaN
        Console.WriteLine(Math.Log(negativeInfinity));
    }
}
```

**输出：**

```cs
1.51512723296286
-Infinity
NaN
NaN
Infinity
NaN
```

## Math.Log(Double, Double) 方法

此方法用于返回指定底数中指定数字的对数。

**语法：**

```cs
public static double Log(double val, double base)
```

**参数：**

> **val**：是要计算对数的指定数字，类型为 `System.Double`。
>
> **base**：是对数的底数，类型为 `System.Double`。

**返回值：** 返回 `val` 以 `base` 为底的对数，类型为 `System.Double`。

**注意：** 返回值始终取决于传递的参数。下表描述了不同的情况：

| val 参数 | base 参数 | 返回值 |
| :--- | :--- | :--- |
| val > 0 | (0 < base < 1) 或 (base > 1) | log<sub>base</sub>(val) |
| val < 0 | 任何值 | `NaN` |
| 任何值 | base < 0 | `NaN` |
| val = 1 | base = 0 | `NaN` |
| val = 1 | base = +ve Infinity | `NaN` |
| val = `NaN` | 任何值 | `NaN` |
| 任何值 | base = `NaN` | `NaN` |
| 任何值 | base = 1 | `NaN` |
| val = 0 | (0 < base < 1) | +ve Infinity |
| val = 0 | base > 1 | -ve Infinity |
| val = +ve Infinity | (0 < base < 1) | -ve Infinity |
| val = +ve Infinity | base > 1 | +ve Infinity |
| val = 1 | base = 0 | Zero |
| val = 1 | base = +ve Infinity | Zero |

**示例：**

```cs
// C# program to demonstrate working
// of Math.Log(Double, Double) method
using System;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {
        // Here val = 1.3 and base is 0.3 then 
        // output will be logarithm of given value
        Console.WriteLine(Math.Log(1.3, 0.3));

        // Here val is 0.5 and base > 1 then output 
        // will be -0.5
        Console.WriteLine(Math.Log(0.5, 4));

        // Here val is 0.7 and base = 1 then output 
        // will be NaN
        Console.WriteLine(Math.Log(0.7, 1));

        // Here val is 0.7 and base is NaN then output 
        // will be NaN
        Console.WriteLine(Math.Log(0.7, Double.NaN));
    }
}
```

**输出：**

```cs
-0.217915440884381
-0.5
NaN
NaN
```

**参考文献：**

*   [https://msdn.microsoft.com/en-us/library/x80ywz41(v=vs.110).aspx](https://msdn.microsoft.com/en-us/library/x80ywz41(v=vs.110).aspx)
*   [https://msdn.microsoft.com/en-us/library/hd50b6h5(v=vs.110).aspx](https://msdn.microsoft.com/en-us/library/hd50b6h5(v=vs.110).aspx)