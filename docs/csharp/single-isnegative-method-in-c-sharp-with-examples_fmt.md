# C# 中的 Single.IsNegative() 方法示例

> 原文：[https://www.geeksforgeeks.org/single-isnegative-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/single-isnegative-method-in-c-sharp-with-examples/)

`Single.IsNegative(Single)` 方法用于返回一个值，该值指示指定的数字是否为负数。

> **语法：** `public static bool IsNegative(float f);`
>
> **返回值：** 如果 `f` 的计算结果为负，则该方法返回 `true`，否则返回 `false`。

以下程序说明了 `Single.IsNegative()` 方法的使用：

**例 1：**

```cs
// C# program to demonstrate the
// Single.IsNegative() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing value1
        float value1 = 1011.5615f;

        // using IsNegative() method
        bool value = Single.IsNegative(value1);

        // Displaying the result
        if (value)
            Console.WriteLine("{0} is Negative", value1);
        else
            Console.WriteLine("{0} is not Negative", value1);
    }
}
```

**输出：**

```cs
1011.562 is not Negative
```

**例 2：**

```cs
// C# program to demonstrate the
// Single.IsNegative() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing value1
        float value1 = -10.651f;

        // using IsNegative() method
        bool value = Single.IsNegative(value1);

        // Displaying the result
        if (value)
            Console.WriteLine("{0} is Negative", value1);
        else
            Console.WriteLine("{0} is not Negative", value1);
    }
}
```

**输出：**

```cs
-10.651 is Negative
```

**参考：**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.single.isnegative?view=netstandard-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.single.isnegative?view=netstandard-2.1)