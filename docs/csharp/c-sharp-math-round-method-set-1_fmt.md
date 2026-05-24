# C# | Math.Round() 方法 | Set–1

> 原文: [https://www.geeksforgeeks.org/c-sharp-math-round-method-set-1/](https://www.geeksforgeeks.org/c-sharp-math-round-method-set-1/)

在 C# 中，`Math.Round()` 是一种数学类方法，用于将一个值舍入到最接近的整数或小数位数。通过更改传递的参数的数量和类型，可以重载此方法。`Math.Round()` 方法的重载列表中总共有 8 个方法。这里只讨论 4 种方法，其余 4 种方法在 *[C# | Math.Round() 方法 | Set–2](https://www.geeksforgeeks.org/c-math-round-method-set-2/)* 中讨论。

*   `Math.Round(Double)`
*   `Math.Round(Double, Int32)`
*   `Math.Round(Decimal)`
*   `Math.Round(Decimal, Int32)`
*   [Math.Round(Double, Int32, MidpointRounding)](https://www.geeksforgeeks.org/c-math-round-method-set-2/)
*   [Math.Round(Decimal, MidpointRounding)](https://www.geeksforgeeks.org/c-math-round-method-set-2/)
*   [Math.Round(Decimal, Int32, MidpointRounding)](https://www.geeksforgeeks.org/c-math-round-method-set-2/)

## Math.Round(Double)

此方法将双精度浮点值舍入到最接近的整数值。

**语法:**

```cs
public static double Round(double x)
```

**参数:**

> **x** : 要取整的双浮点数。该参数的类型为 `System.Double`。

**返回类型:** 返回最接近 `x` 的整数，返回类型为 `System.Double`。

**注:** 如果 `x` 的小数部分在两个整数中间，其中一个是偶数，另一个是奇数，则返回偶数。

**示例:**

```cs
// C# program to demonstrate the 
// Math.Round(Double) method
using System;

class Geeks {

    // Main method
    static void Main(string[] args)
    {

        // Case-1
        // A double value whose fractional part is 
        // less than the halfway between two 
        // consecutive integers
        Double dx1 = 12.434565d;

        // Output value will be 12
        Console.WriteLine("Rounded value of " + dx1 + 
                          " is " + Math.Round(dx1));

        // Case-2
        // A double value whose fractional part is 
        // greater than the halfway between two 
        // consecutive integers
        Double dx2 = 12.634565d;

        // Output value will be 13
        Console.WriteLine("Rounded value of " + dx2 + 
                          " is " + Math.Round(dx2));
    }
}
```

**Output:**

```cs
Rounded value of 12.434565 is 12
Rounded value of 12.634565 is 13
```

**说明:** 在上面的代码中，假设用户想要将上面指定的双精度值舍入到最接近的整数。所以编译器将首先检查那个双精度值是大于还是小于那个双精度值的偶数和奇数整数值。如果它小于中间值，它的输出将是地板值，否则如果大于中间值，它的输出将是天花板值。

## Math.Round(Double, Int32)

此方法将双精度浮点值舍入到指定的小数位数。

**语法:**

```cs
public static double Round(double x, Int32 y)
```

**参数:**

> **x** : 要取整的双浮点数。该参数的类型为 `System.Double`。
> **y** : 是返回值的小数位数。该参数类型为 `System.Int32`。

**返回类型:** 返回最接近 `x` 的整数，其中包含的小数位数等于 `y`，返回类型为 `System.Double`。

**异常:** 如果 `y` 的值小于 0 或大于 15，此方法将给出 `ArgumentOutOfRangeException`。

**示例:**

```cs
// C# program to demonstrate the 
// Math.Round(Double, Int32) method
using System;

class Geeks {

    // Main method
    static void Main(string[] args)
    {

        // double type
        Double dx1 = 12.434565d;

        // using method
        Console.WriteLine("Rounded value of " + dx1 + 
                          " is " + Math.Round(dx1, 4));

        // double type
        Double dx2 = 12.634565d;

        // using method
        Console.WriteLine("Rounded value of " + dx2 + 
                          " is " + Math.Round(dx2,2));
    }
}
```

**Output:**

```cs
Rounded value of 12.434565 is 12.4346
Rounded value of 12.634565 is 12.63
```

**说明:** 方法会检查指定小数位数旁边的数字是否大于等于 5。如果大于或等于 5，则递增前一个数字，否则前一个数字保持不变。

## Math.Round(Decimal)

此方法将精度为 128 位的十进制值舍入到最接近的整数值。

**语法:**

```cs
public static decimal Round(decimal x)
```

**参数:**

> **x** : 要四舍五入的是十进制数。该参数的类型为 `System.Decimal`。

**返回类型:** 返回最接近 `x` 的整数，返回类型为 `System.Decimal`。

**注:** 如果 `x` 的小数部分在两个整数中间，其中一个是偶数，另一个是奇数，则返回偶数。

**示例:**

```cs
// C# program to demonstrate the 
// Math.Round(Decimal) method
using System;

class Geeks {

    // Main method
    static void Main(string[] args)
    {

        // Case-1
        // A decimal value whose fractional part is 
        // less than the halfway between two 
        // consecutive integers
        Decimal dec1 = 12.345m;

        Console.WriteLine("Value of dec1 is " + dec1);

        Console.WriteLine("Rounded value of " + dec1 + 
                          " is " + Math.Round(dec1));

        // Case-2
        // A double value whose fractional part is 
        // greater than the halfway between two 
        // consecutive integers
        Decimal dec2 = 12.785m;

        Console.WriteLine("Value of dec2 is " + dec2);

        Console.WriteLine("Rounded value of " + dec2 + 
                          " is " + Math.Round(dec2));
    }
}
```

**Output:**

```cs
Value of dec1 is 12.345
Rounded value of 12.345 is 12
Value of dec2 is 12.785
Rounded value of 12.785 is 13
```

## Math.Round(Decimal, Int32)

此方法将十进制值舍入到指定的小数位数。

**语法:**

```cs
public static decimal Round(decimal x, Int32 y)
```

**参数:**

> **x** : 要四舍五入的十进制数。该参数的类型为 `System.Decimal`。
> **y** : 是返回值的小数位数。该参数类型为 `System.Int32`。

**返回类型:** 返回最接近 `x` 的整数，其中包含的小数位数等于 `y`，返回类型为 `System.Decimal`。

**异常:** 如果 `y` 的值小于 0 或大于 15，该方法将给出 `ArgumentOutOfRangeException`，如果结果超出十进制范围，则给出 `OverflowException`。

**示例:**

```cs
// C# program to demonstrate the 
// Math.Round(Decimal, Int32) method
using System;

class Geeks {

    // Main Method
    static void Main(string[] args)
    {

        // Case - 1
        // The value of digit after specified 
        // number is less than 5 & Here y = 3
        Decimal dx1 = 12.2234565m;

        // Output value will be 12.223
        Console.WriteLine("Rounded value of " + dx1 + 
                          " is " + Math.Round(dx1, 3));

        // Case - 2
        // The value of digit after specified 
        // number is greater than 5 & Here y = 4
        Decimal dx2 = 12.8734765m;

        // Output value will be 12.8735
        Console.WriteLine("Rounded value of " + dx2 + 
                          " is " + Math.Round(dx2, 4));

    }
}
```

**Output:**

```cs
Rounded value of 12.2234565 is 12.223
Rounded value of 12.8734765 is 12.8735
```

**注意:** 上述十进制值的代码的工作方式与二进制值类似。十进制类型和双精度类型之间的唯一区别在于精度的概念，即在双精度的情况下，精度是 64 位，而在十进制的情况下，精度是 128 位。

**参考:** [https://docs.microsoft.com/en-us/dotnet/api/system.math.round?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.math.round?view=netframework-4.7.2)