# 单身。C# 中的 IsPositiveInfinity()方法，带示例

> 原文:[https://www . geeksforgeeks . org/single-is positiveinfinity-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/single-ispositiveinfinity-method-in-c-sharp-with-examples/)

在 C# 中 ***单。*是单结构方法。此方法用于检查指定的浮点值是否计算为正无穷大。在某些浮点运算中，有可能获得正无穷大的结果。*例如:*如果任何正值被零除，就会产生正无穷大。**

> **语法:**公共静态 bool is positiveInfinity(float f)；
> 
> **参数:**
> *f* :是*系统类型的单精度浮点数。单*。

**返回类型:**该函数返回一个布尔值*真*，如果指定值评估为正无穷大，否则返回*假*。

**例:**演示*单。is 阳性(单一)法*

```cs
// C# program to illustrate the
// Single.IsPositiveInfinity(Single)
// Method
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

        float zero = 0.0f;
        float value = 10.0f;
        float result = value / zero;

        // Printing result
        Console.WriteLine(result);

        // Check result using IsPositiveInfinity() Method
        Console.WriteLine(Single.IsPositiveInfinity(result));

        // Floating point operation that exceeds
        // Single.MaxValue is Positive Infinity
        result = (1.402823E+38f + ((float)9.985e307));

        // Printing result
        Console.WriteLine(result);

        // Check result using IsPositiveInfinity() Method
        Console.WriteLine(Single.IsPositiveInfinity(result));
    }
}
```

**Output:**

```cs
Infinity
True
Infinity
True

```

**注意:**浮点运算返回*正值*表示溢出情况。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . single . is positiveinfinity？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.single.ispositiveinfinity?view=netstandard-2.1)