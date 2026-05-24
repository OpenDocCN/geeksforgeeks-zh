# C# Math.Truncate() 方法

> 原文: [https://www.geeksforgeeks.org/c-sharp-math-truncate-method/](https://www.geeksforgeeks.org/c-sharp-math-truncate-method/)

在 C# 中，`Math.Truncate()` 是一种数学类方法，用于计算指定十进制数或双精度浮点数的整数部分。通过向该方法传递不同类型的参数，可以重载该方法，如下所示:

*   `Math.Truncate(Decimal)`
*   `Math.Truncate(Double)`

### Math.Truncate(Decimal)

此方法用于计算指定十进制数的整数部分。

**语法:**

```cs
public static decimal Truncate(decimal dec)
```

**参数:**

> `dec`: 是需要截断的指定数字，该参数的类型为 `System.Decimal`。

**返回类型:** 此方法只返回 `dec` 的整数部分，丢弃小数部分。这种方法的类型是 `System.Decimal`。

**示例:**

```cs
// C# Program to illustrate the
// Math.Truncate(Decimal) Method
using System;

class Geeks {

    // Main Method
    public static void Main()
    {

        // variables of Decimal type
        Decimal dec = 45.89511m;
        Decimal dec2 = 54569.478021m;

        // using function and displaying result
        Console.WriteLine(Math.Truncate(dec));
        Console.WriteLine(Math.Truncate(dec2));
    }
}
```

**输出:**

```cs
45
54569
```

### Math.Truncate(Double)

此方法用于计算指定双精度浮点数的整数部分。

**语法:**

```cs
public static double Truncate(double dob)
```

**参数:**

> `dob`: 是要截断的指定数字，该参数的类型是 `System.Double`。

**返回类型:** 此方法只返回 `dob` 的整数部分，丢弃小数部分。这种方法的类型是 `System.Double`。

**注意:** 如果 `dob` 是 `NaN`，那么方法将返回 `NaN` 值。如果 `dob` 是 `PositiveInfinity`，那么方法将返回 `PositiveInfinity` 值。如果 `dob` 是 `NegativeInfinity`，那么方法将返回 `NegativeInfinity` 值。

**示例:**

```cs
// C# Program to illustrate the
// Math.Truncate(Double) Method
using System;

class Geeks {

    // Main Method
    public static void Main()
    {

        // variables of Double type
        Double dob = 45649.25649800;
        Double dob2 = 2000150.2654459780;

        // using function and displaying result
        Console.WriteLine(Math.Truncate(dob));
        Console.WriteLine(Math.Truncate(dob2));
    }
}
```

**输出:**

```cs
45649
2000150
```

还有其他方法可以截断数字，比如将数字转换为整数，但这并不总是有效的。与其他数学方法相比，这可能是执行所需任务的最可靠的方法。