# C# | `Math.Ceiling()` 方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-math-ceiling-method/](https://www.geeksforgeeks.org/c-sharp-math-ceiling-method/)

在 C# 中，`Math.Ceiling()` 是一种数学类的方法。此方法用于查找大于或等于传递参数的`最小整数`。`Ceiling` 方法同时操作 `decimal` 和 `double` 两种类型。这个方法可以通过传递不同的参数来重载。

*   `Math.Ceiling(decimal)` 方法
*   `Math.Ceiling(double)` 方法

## `Math.Ceiling(decimal)` 方法

此方法用于返回大于或等于参数列表中指定小数的`最小整数值`。

**语法：**

```cs
public static decimal Ceiling(decimal d)
```

**参数：**

> **`decimal d`**：是`系统类型`的十进制数 (`System.Decimal`)。

**返回类型：** 该函数返回大于等于 `d` 的最小整数值，该方法的返回类型为`System.Decimal`，并返回一个小数而不是整型。

**例：**

```cs
Input  : 888.765M;
Output : 889

Input  : -20002.999M
Output : -20002
```

**程序：** 演示 `Math.Ceiling(decimal)` 方法。

```cs
// C# program to illustrate the
// Math.Ceiling(Decimal) function
using System;

class SudoPlacement {

    // Main method
    static void Main()
    {

        // Input decimal value.
        decimal decim_n1 = 2.10M;
        decimal decim_n2 = -99.90M;
        decimal decim_n3 = 33.001M;

        // Calculate Ceiling values by
        // Using Math.Ceiling() function
        decimal ceil_t1 = Math.Ceiling(decim_n1);
        decimal ceil_t2 = Math.Ceiling(decim_n2);
        decimal ceil_t3 = Math.Ceiling(decim_n3);

        // Print First values and Ceiling
        Console.WriteLine("Input Value  = " + decim_n1);
        Console.WriteLine("Ceiling value = " + ceil_t1);

        // Print Second values and Ceiling
        Console.WriteLine("Input Value  = " + decim_n2);
        Console.WriteLine("Ceiling value = " + ceil_t2);

        // Print third values and Ceiling
        Console.WriteLine("Input Value  = " + decim_n3);
        Console.WriteLine("Ceiling value = " + ceil_t3);
    }
}
```

**Output：**

```cs
Input Value  = 2.10
Ceiling value = 3
Input Value  = -99.90
Ceiling value = -99
Input Value  = 33.001
Ceiling value = 34
```

## `Math.Ceiling(double)` 方法

此方法用于返回大于或等于参数列表中指定的双精度浮点数的最小整数值。

**语法：**

```cs
public static double Ceiling(double d)
```

**参数：**

> **`double d`**：是`系统类型`的双精度浮点数 (`System.Double`)。

**返回类型：** 该方法返回大于或等于 `d` 的最小整数值，如果 `d` 等于 `NaN`、`NegativeInfinity` 或 `PositiveInfinity`，则返回该值。这种方法的返回类型是`System.Double`。

**例：**

```cs
Input  : 10.1  
Output : 11

Input  : -2222.2220
Output : -2222
```

**程序：** 演示 `Math.Ceiling(double)` 方法。

```cs
// C# program to illustrate the
// Math.Ceiling(Double) function
using System;

class SudoPlacement {

    // Main method
    static void Main()
    {

        // Input different Double value.
        double n1 = 101.10;
        double n2 = -1.1;
        double n3 = 9222.1000;

        // Calculate Ceiling values by
        // Using Math.Ceiling() function
        double t1 = Math.Ceiling(n1);
        double t2 = Math.Ceiling(n2);
        double t3 = Math.Ceiling(n3);

        // Print First values and Ceiling
        Console.WriteLine("Input Value  = " + n1);
        Console.WriteLine("Ceiling value = " + t1);

        // Print Second values and Ceiling
        Console.WriteLine("Input Value  = " + n2);
        Console.WriteLine("Ceiling value = " + t2);

        // Print third values and Ceiling
        Console.WriteLine("Input Value  = " + n3);
        Console.WriteLine("Ceiling value = " + t3);
    }
}
```

**Output：**

```cs
Input Value  = 101.1
Ceiling value = 102
Input Value  = -1.1
Ceiling value = -1
Input Value  = 9222.1
Ceiling value = 9223
```

**参考文献：**

*   [https://msdn.microsoft.com/en-us/library/1cz5da1c(v=vs.110).aspx](https://msdn.microsoft.com/en-us/library/1cz5da1c(v=vs.110).aspx)
*   [https://msdn.microsoft.com/en-us/library/zx4t0t48(v=vs.110).aspx](https://msdn.microsoft.com/en-us/library/zx4t0t48(v=vs.110).aspx)