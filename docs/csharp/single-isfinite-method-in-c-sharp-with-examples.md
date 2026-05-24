# 单身。C# 中的 IsFinite()方法，带示例

> 原文:[https://www . geesforgeks . org/single-is inite-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/single-isfinite-method-in-c-sharp-with-examples/)

**单身。IsFinite()方法**用于检查浮点值是否越界。

> **语法:**公共静态 bool IsFinite(浮点值)；
> 
> **返回值:**如果值是有限的，该方法返回*真*，否则返回*假*。

以下程序说明了 *Single 的使用。IsFinite()* 方法:

**例 1:**

```cs
// C# program to demonstrate the
// Single.IsFinite() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing value1
        float value1 = 1654.268416f;

        // using IsFinite() method
        bool value = Single.IsFinite(value1);

         // Displaying the result
        if (value)
            Console.WriteLine("{0} is finite", value1);
        else
            Console.WriteLine("{0} is not finite", value1);
    }
}
```

**Output:**

```cs
1654.268 is finite

```

**例 2:**

```cs
// C# program to demonstrate the
// Single.IsFinite() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing value1
        float value1 = (float)Math.Pow(2, 10000000);

        // using IsFinite() method
        bool value = Single.IsFinite(value1);

         // Displaying the result
        if (value)
            Console.WriteLine("{0} is finite", value1);
        else
            Console.WriteLine("{0} is not finite", value1);
    }
}
```

**Output:**

```cs
Infinity is not finite

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . single . is inite？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.single.isfinite?view=netstandard-2.1)