# C# 中的 Single.IsNaN() 方法及示例

> 原文: [https://www.geeksforgeeks.org/single-isnan-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/single-isnan-method-in-c-sharp-with-examples/)

在 C# 中，`Single.IsNaN(Single)` 是 `Single` 结构的方法。此方法用于检查指定的浮点值是否不是数字 (NaN)。

> **语法:**
> `public static bool IsNaN(float f);`
>
> **参数:**
> `f` : 是 `System.Single` 类型的单精度浮点数。

**返回类型:** 该函数返回一个布尔值，即 `true`，如果指定值不是数字 (NaN)，则返回 `false`。

**示例:**

```cs
// C# program to demonstrate
// Single.IsNaN(Single) method
using System;

class GFG {

    // Main Method
    public static void Main(String[] args)
    {
        // first example
        float f1 = 1.0f / 0.0f;
        bool res = Single.IsNaN(f1);

        // printing the output
        if (res)
            Console.WriteLine(f1 + " is NaN");
        else
            Console.WriteLine(f1 + " is not NaN");

        // second example
        // it will give result
        // NaN
        float f2 = 0.0f / 0.0f;
        bool res1 = Single.IsNaN(f2);

        // printing the output
        if (res1)
            Console.WriteLine(f2 + " is NaN");
        else
            Console.WriteLine(f2 + " is not NaN");
    }
}
```

**Output:**

```cs
Infinity is not NaN
NaN is NaN
```

**注:**

*   如果 `Single` 值为 `PositiveInfinity` 或 `NegativeInfinity`，则该方法返回 `false`。
*   浮点运算返回一个 `NaN`，表示运算结果未定义。

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.single.isnan?view=netstandard-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.single.isnan?view=netstandard-2.1)