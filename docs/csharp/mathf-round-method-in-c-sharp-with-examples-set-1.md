# MathF。C# 中的 Round()方法，带示例| Set–1

> 原文:[https://www . geesforgeks . org/mathf-round-method-in-c-sharp-with-examples-set-1/](https://www.geeksforgeeks.org/mathf-round-method-in-c-sharp-with-examples-set-1/)

在 C# 中 ***MathF。Round()*** 是一个 MathF 类方法，用于将一个值舍入到最接近的整数或小数位数。通过更改传递的参数的数量和类型，可以重载此方法。MathF 的重载列表中有 4 个方法。Round()方法。

***   MathF。 Circle (single) method*   MathF。 Circle (single, Int32) method*   MathF。 Rounding (single, integer 32, midpoint rounding) method*   MathF。 Circle (single and midpoint circle) method**

在这里，我们将讨论前两种方法。

#### MathF。圆(单)法

此方法将单精度浮点值舍入到最接近的整数值。

> **语法:**公共静态 float Round(float x)；
> 这里， **x** 是一个要四舍五入的单浮点数。该参数类型为**系统。单**。
> 
> **返回类型:**返回最接近 x 的整数，返回类型为**系统。单**。

**注:**如果 **x** 的小数部分在两个整数中间，其中一个是偶数，另一个是奇数，则返回偶数。

**示例:**

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

**Output:**

```cs
Rounded value of 12.43456 is 12
Rounded value of 12.63457 is 13

```

#### MathF。圆形(单一，整数 32)方法

此方法将单精度浮点值舍入到指定的小数位数。

> **语法:**公共静态 float Round (float x，int 位数)；
> 
> **参数:**
> **x** :要取整的单个浮点数。该参数类型为**系统。单**。
> **y** :是返回值中的小数位数。该参数类型为**系统。Int32** 。

**返回类型:**返回最接近 x 的整数，其中包含的小数位数等于 *y* ，返回类型为**系统。单**。

**异常:**如果 *y* 的值小于 0 或大于 15，此方法将给出*argumentout of range Exception*。

**示例:**

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

**Output:**

```cs
Rounded value of 12.43456 is 12.4346
Rounded value of 12.63457 is 12.63

```