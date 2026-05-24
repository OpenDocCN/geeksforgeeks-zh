# C# | Math.Floor() 方法

> 原文: [https://www.geeksforgeeks.org/c-sharp-math-floor-method/](https://www.geeksforgeeks.org/c-sharp-math-floor-method/)

在 C# 中，`Math.Floor()` 是一个 `Math` 类的方法。此方法用于查找最大的整数，该整数小于或等于传递的参数。`Floor` 方法操作 `decimal` 和 `double` 两种类型。这个方法可以通过传递不同的参数来重载。

*   `Math.Floor(Decimal)` 方法
*   `Math.Floor(Double)` 方法

## Math.Floor(Decimal) 方法

此方法用于返回小于或等于参数列表中指定 `decimal` 数的最大整数。

**语法:**

```cs
public static decimal Floor(decimal d)
```

**参数:**

> `decimal d`: 是 `System.Decimal` 类型。

**返回类型:** 该函数返回小于等于 `d` 的最大整数，该方法的返回类型为 `System.Decimal`。

**示例:**

```cs
Input  : 12.9
Output : 12

Input  : -12.9
Output : -13
```

**程序:** 演示 `Math.Floor(Decimal)` 方法。

```cs
// C# program to illustrate the
// Math.Floor(Decimal) function
using System;

public class GFG {

    // Main method
    static public void Main()
    {
        // Different numbers list to find
        // its floor values
        Console.WriteLine(Math.Floor(0.2018));
        Console.WriteLine(Math.Floor(123.123));
        Console.WriteLine(Math.Floor(-0.2));
        Console.WriteLine(Math.Floor(0.0));
        Console.WriteLine(Math.Floor(34.67M));
    }
}
```

**输出:**

```cs

```

## Math.Floor(Double) 方法

此方法用于返回小于或等于参数列表中指定的 `double` 浮点数的最大整数。

**语法:**

```cs
public static double Floor(double d)
```

**参数:**

> `double d`: 是 `System.Double` 类型的数字。

**返回类型:** 该方法返回小于或等于 `d` 的最大整数，如果 `d` 等于 `NaN`、`NegativeInfinity` 或 `PositiveInfinity`，则返回该值。这种方法的返回类型是 `System.Double`。

**示例:**

```cs
Input  : 987654321.012 
Output : 987654321

Input  : -99999
Output : -100000
```

**程序:** 演示 `Math.Floor(Double)` 方法。

```cs
// C# program to illustrate the
// Math.Floor(Double) function
using System;
class GFG {

    // Main method 
    static void Main()
    {
        // Two values.
        double n1 = 0.2018;
        double n2 = 123.123;
        double n3 = -2.2;
        double n4 = -123.123;

        // Take floors of these values.
        double floor1 = Math.Floor(n1);
        double floor2 = Math.Floor(n2);
        double floor3 = Math.Floor(n3);
        double floor4 = Math.Floor(n4);

        // Print First values and floor
        Console.WriteLine("value n1 = " + n1);
        Console.WriteLine("Floor1 values is = " + floor1);

        // Print 2nd values and floor
        Console.WriteLine("value n2 = " + n2);
        Console.WriteLine("Floor2 values is = " + floor2);

        // Print 3rd values and floor
        Console.WriteLine("value n3 = " + n3);
        Console.WriteLine("Floor3 values is = " + floor3);

        // Print 4th values and floor
        Console.WriteLine("value n4 = " + n4);
        Console.WriteLine("Floor4 values is = " + floor4);
    }
}
```

**输出:**

```cs
value n1 = 0.2018
Floor1 values is = 0
value n2 = 123.123
Floor2 values is = 123
value n3 = -2.2
Floor3 values is = -3
value n4 = -123.123
Floor4 values is = -124
```

**参考:** [https://msdn.microsoft.com/en-us/library/system.math.floor(v=vs.110).aspx](https://msdn.microsoft.com/en-us/library/system.math.floor(v=vs.110).aspx)