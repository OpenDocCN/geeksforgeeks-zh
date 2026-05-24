# UInt64。C# 中的最小值字段，示例

> 原文:[https://www . geeksforgeeks . org/uint 64-min value-field-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/uint64-minvalue-field-in-c-sharp-with-examples/)

*UInt64* 结构的**最小值**属性或字段用于表示 64 位无符号长整数的最小可能值，即 *ulong* 数据类型。该字段的值为常量意味着用户不能更改该字段的值。该字段的值为 **0** 。这可以防止运行时出现*溢出异常*。

**语法:**

```cs
public const ulong MinValue = 0;
```

**返回值:**该字段始终返回 0。

**例:**

```cs
// C# program to illustrate the
// UInt64.MinValue Field
using System;

class GFG {

    // Main Method
    static public void Main()
    {
        // display the Minimum
        // value of UInt64 struct
        Console.WriteLine("Minimum Value is: " + UInt64.MinValue);

        // taking a variable
        ulong var1 = 2382373544;

        if (var1.Equals(UInt64.MinValue)) 
        {
            Console.WriteLine("Equal..!!");
            Console.WriteLine("Type of var1 is: {0}",
                                 var1.GetTypeCode());
        }

        else 
        {
            Console.WriteLine("Not equal..!!");
            Console.WriteLine("Type of var1 is: {0}",
                                 var1.GetTypeCode());
        }
    }
}
```

**输出:**

```cs
Minimum Value is: 0
Not equal..!!
Type of var1 is: UInt64

```

**参考:**

*   [https://docs。微软。com/en-us/dotnet/API/system。uint 64。最小值？视图=netstandard-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uint64.minvalue?view=netstandard-2.1)