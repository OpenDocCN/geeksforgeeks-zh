# MathF.Round() 方法在 C# 中的使用（含示例）- Set 1

> 原文：[https://www.geeksforgeeks.org/mathf-round-method-in-c-sharp-with-examples-set-1/](https://www.geeksforgeeks.org/mathf-round-method-in-c-sharp-with-examples-set-1/)

在 C# 中，`MathF.Round()` 是 `MathF` 类的一个方法，用于将一个值舍入到最接近的整数或指定的小数位数。通过改变传递参数的数量和类型，可以重载此方法。`MathF` 类的重载列表中有 4 个 `Round()` 方法。

*   `MathF.Round(Single)` 方法
*   `MathF.Round(Single, Int32)` 方法
*   `MathF.Round(Single, Int32, MidpointRounding)` 方法
*   `MathF.Round(Single, MidpointRounding)` 方法

在这里，我们将讨论前两种方法。

## MathF.Round(Single) 方法

此方法将单精度浮点值舍入到最接近的整数值。

> **语法：**
> `public static float Round(float x);`
> 这里，`x` 是一个要四舍五入的单精度浮点数。该参数类型为 `System.Single`。
>
> **返回类型：** 返回最接近 `x` 的整数，返回类型为 `System.Single`。

**注意：** 如果 `x` 的小数部分恰好在两个整数的中间（即 .5），则返回其中的偶数。

**示例：**

```cs
// C# program to demonstrate the
// MathF.Round(Single) method
using System;

class Geeks {

    // Main method
    static void Main(string[] args)
    {
        // Case-1
        // A float value whose fractional part is
        // less than the halfway between two
        // consecutive integers
        float dx1 = 12.434565f;

        // Output value will be 12
        Console.WriteLine("Rounded value of " + dx1 +
                          " is " + MathF.Round(dx1));

        // Case-2
        // A float value whose fractional part is
        // greater than the halfway between two
        // consecutive integers
        float dx2 = 12.634565f;

        // Output value will be 13
        Console.WriteLine("Rounded value of " + dx2 +
                          " is " + MathF.Round(dx2));
    }
}
```

**输出：**

```cs
Rounded value of 12.43456 is 12
Rounded value of 12.63457 is 13
```

## MathF.Round(Single, Int32) 方法

此方法将单精度浮点值舍入到指定的小数位数。

> **语法：**
> `public static float Round(float x, int digits);`
>
> **参数：**
> `x`：要取整的单精度浮点数。该参数类型为 `System.Single`。
> `digits`：返回值中的小数位数。该参数类型为 `System.Int32`。

**返回类型：** 返回最接近 `x` 的值，其中包含的小数位数等于 `digits`，返回类型为 `System.Single`。

**异常：** 如果 `digits` 的值小于 0 或大于 15，此方法将抛出 `ArgumentOutOfRangeException`。

**示例：**

```cs
// C# program to demonstrate the
// MathF.Round(Single, Int32) Method
using System;

class Geeks {

    // Main method
    static void Main(string[] args)
    {
        // float type
        float dx1 = 12.434565f;

        // using method
        Console.WriteLine("Rounded value of " + dx1 +
                      " is " + MathF.Round(dx1, 4));

        // float type
        float dx2 = 12.634565f;

        // using method
        Console.WriteLine("Rounded value of " + dx2 +
                       " is " + MathF.Round(dx2, 2));
    }
}
```

**输出：**

```cs
Rounded value of 12.43456 is 12.4346
Rounded value of 12.63457 is 12.63
```