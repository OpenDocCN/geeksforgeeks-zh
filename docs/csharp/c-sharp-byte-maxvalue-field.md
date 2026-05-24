# C# | Byte。最大值字段

> 原文:[https://www.geeksforgeeks.org/c-sharp-byte-maxvalue-field/](https://www.geeksforgeeks.org/c-sharp-byte-maxvalue-field/)

字节结构的*最大值*字段用于表示字节数据类型的最大值。该字段的值为常量意味着用户不能更改该字段的值。该字段的值为 255。其十六进制值为 *0xFF* 。

**语法:**

```cs
public const byte MaxValue = 255;
```

**返回值:**该字段始终返回 255。

**例:**

```cs
// C# program to illustrate the
// Byte.MaxValue Field
using System;

class GFG {

    // Main Method
    static public void Main()
    {
        // display the Maximum
        // value of Byte struct
        Console.WriteLine("Maximum Value is: " + Byte.MaxValue);

        // taking a variable
        byte var1 = 255;

        if (var1.Equals(Byte.MaxValue)) 
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
Maximum Value is: 255
Equal..!!
Type of var1 is: Byte

```

**参考:**

*   [https://docs。微软。com/en-us/dotnet/API/system。字节。maxvalue？视图=netstandard-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.byte.maxvalue?view=netstandard-2.1)