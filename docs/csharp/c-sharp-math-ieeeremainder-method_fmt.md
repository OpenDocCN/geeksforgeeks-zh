# C# | 数学.IEEERemainder()方法

> 原文: [https://www.geeksforgeeks.org/c-sharp-math-ieeeremainder-method/](https://www.geeksforgeeks.org/c-sharp-math-ieeeremainder-method/)

在 C# 中，`IEEERemainder()` 是一个 `Math` 类方法，用于返回一个指定数除以另一个指定数所得的余数。

## 语法:

```cs
public static double IEEERemainder (double a, double b);
```

## 参数:

> **a:** 是 `System` 类型的被除数 (`double`)。
> **b:** 是 `System` 类型的除数 (`double`)。

## 返回类型:

该方法返回一个等于 `a - (b * Q)` 的数字，其中 `Q` 是 `a / b` 舍入到最接近整数的商 (`System.Double`)。

## 注:

*   如果 `a / b` 落在两个整数中间，则返回偶数。
*   如果 `a - (b * Q)` 为零，则如果 `a` 为正，则返回正值零，如果 `a` 为负，则返回负值零。
*   如果 `b` = 0，则返回 `NaN`。

## IEEERemainder 和余数运算符的区别:

两者都用于在除法后返回余数，但它们使用的公式不同。`IEEERemainder` 方法的公式为:

```cs
IEEERemainder = dividend - (divisor * Math.Round(dividend / divisor))
```

*余数运算符*的公式为:

```cs
Remainder = (Math.Abs(dividend) - (Math.Abs(divisor) *  
            (Math.Floor(Math.Abs(dividend) / Math.Abs(divisor))))) *   
            Math.Sign(dividend)
```

## 示例:

### C#

```cs
// C# Program to illustrate the
// Math.IEEERemainder() Method
using System;

class Geeks
{

    // method to calculate the remainder
    private static void DisplayRemainder(double num1, double num2)
    {

        var calculation = $"{num1} / {num2} = ";

        // calculating IEEE Remainder
        var ieeerem = Math.IEEERemainder(num1, num2);

        // using remainder operator
        var rem_op = num1 % num2;

        Console.WriteLine($"{calculation,-16} {ieeerem,18} {rem_op,20}");
    }

    // Main Method
    public static void Main()
    {

        Console.WriteLine($"{"IEEERemainder",35} {"Remainder Operator",20}");

        // calling the method
        DisplayRemainder(0, 1);
        DisplayRemainder(-4, 8);
        DisplayRemainder(1, 0);
        DisplayRemainder(-1, -0);
        DisplayRemainder(145, 7);
        DisplayRemainder(18.52, 2);
        DisplayRemainder(42.26, 4.2);
    }
}
```

## 输出:

```cs
                      IEEERemainder   Remainder Operator
0 / 1 =                           0                    0
-4 / 8 =                         -4                   -4
1 / 0 =                         NaN                  NaN
-1 / 0 =                        NaN                  NaN
145 / 7 =                        -2                    5
18.52 / 2 =                    0.52                 0.52
42.26 / 4.2 =     0.259999999999998    0.259999999999996
```

**参考:** [https://docs.microsoft.com/zh-cn/dotnet/api/system.math.ieeeremainder?view=netframework-4.7.2](https://docs.microsoft.com/zh-cn/dotnet/api/system.math.ieeeremainder?view=netframework-4.7.2)