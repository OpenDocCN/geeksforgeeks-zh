# Int64。C# 中的最大值字段，示例

> 原文:[https://www . geesforgeks . org/int 64-maxvalue-field-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/int64-maxvalue-field-in-c-sharp-with-examples/)

Int64 Struct 的 MaxValue 字段或属性用于表示 Int64 的最大值。该字段的值为常量意味着用户不能更改该字段的值。该字段的值为 9223372036854775807。其十六进制值为 *0x7FFFFFFFFFFFFFFF* 。

**语法:**

```cs
public const long MaxValue = 9223372036854775807;
```

**返回值:**该字段始终返回 9223372036854775807。

**例:**

```cs
// C# program to illustrate the
// Int64.MaxValue Field
using System;

class GFG {

    // Main Method
    static public void Main()
    {
        // display the Maximum
        // value of Int64 struct
        Console.WriteLine("Maximum Value is: "+
                            Int64.MaxValue);

        // taking a variable                 
        long var1 = 93422337368375807;

        if(var1.Equals(Int64.MaxValue))
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
Maximum Value is: 9223372036854775807
Not equal..!!
Type of var1 is: Int64

```

**参考:**

*   [https://docs。微软。com/en-us/dotnet/API/system。int 64。maxvalue？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.int64.maxvalue?view=netframework-4.7.2)