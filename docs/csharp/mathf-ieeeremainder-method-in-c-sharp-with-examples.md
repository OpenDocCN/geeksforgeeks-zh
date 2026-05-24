# MathF。C# 中的 IEEERemainder()方法及示例

> 原文:[https://www . geesforgeks . org/mathf-ieeereminder-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/mathf-ieeeremainder-method-in-c-sharp-with-examples/)

在 C# 中，***ieeereminder(Single)***是一个 MathF 类方法，用于返回一个指定数除以另一个指定数所得的余数。

> **语法:**公共静态 float ieeereminder(float x，float y)；
> 
> **参数:**
> **x:** 是*系统类型的红利。单*。
> **y:** 是*型系统的除数。单*。

**返回类型:**此方法返回一个等于*x*–(*y*Q 的数字，其中 *Q* 是 *x / y* 的商，四舍五入到类型*系统的最接近整数。单*。
**注:**

*   如果 *x* / *y* 落在两个整数中间，则返回偶数。
*   如果*x*–(*y*Q)为零，则如果 *x* 为正，则返回正值零，如果 *y* 为负，则返回负值零。
*   如果 *y* = 0，则返回 *NaN* 。

【IEEERemainder 和余数运算符的区别:两者都用于在除法后返回余数，但它们使用的公式不同。*积分积分法的公式为:* 

```cs
IEEERemainder = dividend - (divisor * MathF.Round(dividend / divisor))
```

*余数运算符*的公式为:

```cs
Remainder = (MathF.Abs(dividend) - (MathF.Abs(divisor) *  
            (MathF.Floor(MathF.Abs(dividend) / MathF.Abs(divisor))))) *   
             MathF.Sign(dividend)
```

**例:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# Program to illustrate the use of
// MathF.IEEERemainder(Single, Single)
// Method
using System;

class Geeks {

    // Method to calculate the remainder
    private static void DisplayRemainder(float x,
                                        float y)
    {

        var calculation = {content}quot;{x} / {y} = ";

        // calculating IEEE Remainder
        var ieeerem = MathF.IEEERemainder(x, y);

        // using remainder operator
        var rem_op = x % y;

        Console.WriteLine({content}quot;{calculation,-16} {ieeerem,18} {rem_op,20}");
    }

    // Main Method
    public static void Main()
    {

        Console.WriteLine({content}quot;{"IEEERemainder",35} {"Remainder Operator",20}");

        // calling the method
        DisplayRemainder(0f, 1f);
        DisplayRemainder(-4f, 8f);
        DisplayRemainder(1f, 0f);
        DisplayRemainder(-1f, -0f);
        DisplayRemainder(175f, 6f);
        DisplayRemainder(784.52f, 124f);
        DisplayRemainder(92.267f, 3.259f);
    }
}
```

**Output:** 

```cs
IEEERemainder   Remainder Operator
0 / 1 =                           0                    0
-4 / 8 =                         -4                   -4
1 / 0 =                         NaN                  NaN
-1 / 0 =                        NaN                  NaN
175 / 6 =                         1                    1
784.52 / 124 =             40.52002             40.52002
92.267 / 3.259 =            1.014997             1.014997
```