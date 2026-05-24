# C# | Math.Round() 方法 | Set–2

> 原文: [https://www.geeksforgeeks.org/c-sharp-math-round-method-set-2/](https://www.geeksforgeeks.org/c-sharp-math-round-method-set-2/)

在 C# 中，`Math.Round()` 是一种数学类方法，用于将一个值舍入到最接近的整数或小数位数。此方法还有另一个重载，使用该重载，您可以指定返回值小数点后的位数。它返回数字的最近值，精度等于传递的第二个参数。如果要舍入的值正好介于偶数和奇数之间，则返回偶数。`Math.Round()` 适用于 IEEE 标准 754，第 4 节。

通过更改传递的参数的数量和类型，可以重载此方法。`Math.Round()` 方法的重载列表中总共有 8 种方法，其中 **4** 种已经在 [C# | Math.Round() 方法 | Set–1](https://www.geeksforgeeks.org/c-math-round-method-set-1/) 中讨论过了。

*   [`Math.Round(Double)`](https://www.geeksforgeeks.org/c-math-round-method-set-1/)
*   [`Math.Round(Double, Int32)`](https://www.geeksforgeeks.org/c-math-round-method-set-1/)
*   [`Math.Round(Decimal)`](https://www.geeksforgeeks.org/c-math-round-method-set-1/)
*   [`Math.Round(Decimal, Int32)`](https://www.geeksforgeeks.org/c-math-round-method-set-1/)
*   `Math.Round(Double, Int32, MidpointRounding)`
*   `Math.Round(Double, MidpointRounding)`
*   `Math.Round(Decimal, Int32, MidpointRounding)`
*   `Math.Round(Decimal, MidpointRounding)`

## Math.Round(Double, Int32, MidpointRounding)

此方法用于将双精度浮点值舍入到指定的小数位数。参数指定如果值在两个数字中间，如何舍入该值。

### 语法

```cs
public static double Round (double val, int digits, MidpointRounding mode);
```

### 参数

> **val**: 需要四舍五入的双精度浮点数，该参数类型为 `System.Double`。
>
> **digits**: 是返回值中的小数位数，该参数类型为 `System.Int32`。
>
> **mode**: 如果值在另外两个数字中间，作为 `MidpointRounding` 如何舍入该值的规范。

### 返回类型

该方法返回最接近 `val` 的数字，其小数位数等于 `digits`。如果 `val` 的小数位数少于 `digits`，则 `val` 不变地返回。该方法的返回类型为 `System.Double`。

### 异常

*   `ArgumentOutOfRangeException`: 如果 `digits` 小于 0 或大于 15。
*   `ArgumentException`: 如果 `mode` 不是 `MidpointRounding` 的有效值。

### 示例

```cs
// C# program to demonstrate the
// Math.Round(Double, Int32,
// MidpointRounding) method
using System;

class Geeks
{
    // Main Method
    public static void Main()
    {
        // The 4 values are store in an double
        // type array name 'val'
        double[] val = {4.125, 4.135, 4.165, 4.175};

        Console.WriteLine("Rounded values are:");

        // 'foreach' loop iterates through
        // each item from the array 'values'
        // and storing the items in a new
        // variable 'val'
        foreach(double value in val)
        {
            // '{0}' specify the variable 'val' which is
            // in 'foreach' loop and '{1}' specify the
            // rounded value, here '2' defines the number
            // of digit after point, e.g. 4.135 == 4.14,
            // after '4.' there is 2 digits'.14'
            // and here '.ToEven' select the nearest even
            // number e.g 4.125 == 4.12, here nearest even
            // number is '12',
            Console.WriteLine("{0} == {1}", value, Math.Round(value, 2,
                                         MidpointRounding.ToEven));
        }
    }
}
```

### 输出

```cs
Rounded values are:
4.125 == 4.12
4.135 == 4.14
4.165 == 4.16
4.175 == 4.18
```