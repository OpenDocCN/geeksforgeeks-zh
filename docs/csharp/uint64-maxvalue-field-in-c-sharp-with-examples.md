# UInt64。C# 中的最大值字段，示例

> 原文:[https://www . geesforgeks . org/uint 64-maxvalue-field-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/uint64-maxvalue-field-in-c-sharp-with-examples/)

UInt64 Struct 的 MaxValue 字段用于表示 64 位无符号长整数的最大值。该字段的值为常量意味着用户不能更改该字段的值。该字段的值为 18446744073709551615。其十六进制值为 *0xFFFFFFFFFFFFFFFF* 。用于避免运行时出现*飞越异常*。

**语法:**

```cs
public const ulong MaxValue = 18446744073709551615;
```

**返回值:**该字段始终返回 18446744073709551615。

**例:**

```cs
// C# program to illustrate the
// UInt64.MaxValue Field
using System;

class GFG {

    // Main Method
    static public void Main()
    {
        // display the Maximum
        // value of UInt64 struct
        Console.WriteLine("Maximum Value is: " + UInt64.MaxValue);

        // taking a variable
        ulong var1 = 93422337368375807;

        if (var1.Equals(UInt64.MaxValue))
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
Maximum Value is: 18446744073709551615
Not equal..!!
Type of var1 is: UInt64

```

**参考:**

*   [https://docs。微软。com/en-us/dotnet/API/system。uint 64。maxvalue？视图=netstandard-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uint64.maxvalue?view=netstandard-2.1)