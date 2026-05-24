# 单身。C# 中的 IsNegativeInfinity()方法，带示例

> 原文:[https://www . geesforgeks . org/single-is negative infinity-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/single-isnegativeinfinity-method-in-c-sharp-with-examples/)

在 C# 中 ***单。*是单结构方法。此方法用于检查指定的浮点值是否计算为负无穷大。在某些浮点运算中，有可能获得负无穷大的结果。*例如:*如果任何负值被零除，就会产生负无穷大。**

> **语法:**公共静态 bool isnegative infinity(float f)；
> **参数:**
> *f* :是*系统类型的单精度浮点数。单*。

**返回类型:**该函数返回一个布尔值*真*，如果指定值评估为负无穷大，否则返回*假*。

**例:**演示*单。IsNegativeInfinity(单)法*:

```cs
// C# program to illustrate the
// Single.IsNegativeInfinity(Single)
// Method
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Dividing a negative number by zero
        // results in Negative infinity.

        // Dividing a number directly by 0
        // produces an error
        // So 0 is stored in a variable first

        float zero = 0.0f;
        float value = -5f;
        float result = value / zero;

        // Printing result
        Console.WriteLine(result);

        // Check result using IsNegativeInfinity() Method
        Console.WriteLine(Single.IsNegativeInfinity(result));

        // Result of floating point operation
        // that is less than Single.MinValue
        // is Negative Infinity

        result = Single.MinValue * 7.9f;

        // Printing result
        Console.WriteLine(result);

        // Check result using IsNegativeInfinity() Method
        Console.WriteLine(Single.IsNegativeInfinity(result));
    }
}
```

**Output:**

```cs
-Infinity
True
-Infinity
True

```

**注:**

*   小于 *Single 的任何浮点运算的结果。MinValue* 被认为是负无穷大。
*   浮点运算返回*正有限性*或*负有限性*以指示溢出条件。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . single . is negative infinity？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.single.isnegativeinfinity?view=netstandard-2.1)