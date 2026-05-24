# 翻倍。C# 中的 IsPositiveInfinity()方法

> 原文:[https://www . geeksforgeeks . org/double-is positiveinfinity-method-in-c-sharp/](https://www.geeksforgeeks.org/double-ispositiveinfinity-method-in-c-sharp/)

在 C# 中 ***加倍。*是一种双重结构方法。此方法用于检查指定值是否计算为正无穷大。在某些浮点运算中，有可能获得正无穷大的结果。*例如:*如果任何正值被零除，就会产生正无穷大。**

> **语法:**公共静态 bool is positiveinfinity(double d)；
> 
> **参数:**
> *d* :是*系统类型的双精度浮点数。双*。

**返回类型:**该函数返回一个布尔值*真*，如果指定值评估为正无穷大，否则返回*假*。

**示例:**

```cs
Input  : d = 10 / 0.0 
Output : True

Input  : d =  7.997e307 + 9.985e307; 
Output : True

```

**代码:**演示替身。是正定性(双重)方法

```cs
// C# program to illustrate the
// Double.IsPositiveInfinity() Method
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Dividing a Positive number by zero
        // results in positive infinity.

        // Dividing a number directly by 0
        // produces an error
        // So 0 is stored in a variable first

        double zero = 0.0;
        double value = 10.0;
        double result = value / zero;

        // Printing result
        Console.WriteLine(result);

        // Check result using IsPositiveInfinity() Method
        Console.WriteLine(Double.IsPositiveInfinity(result));

        // Floating point operation that exceeds
        // Double.MaxValue (i.e 1.7976931348623157E+308)
        // is Positive Infinity

        result = 7.997e307 + 9.985e307;

        // Printing result
        Console.WriteLine(result);

        // Check result using IsPositiveInfinity() Method
        Console.WriteLine(Double.IsPositiveInfinity(result));
    }
}
```

**注:**

*   浮点运算返回*无穷大*(正无穷大)或*-无穷大*(负无穷大)以指示溢出情况。
*   任何超过 Double 的浮点运算的结果。MaxValue(即 1.7976931348623157E+308)被认为是正无穷大。