# Int64.MinValue 字段在 C# 中的示例

> 原文：[https://www.geeksforgeeks.org/int64-minvalue-field-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/int64-minvalue-field-in-c-sharp-with-examples/)

## 介绍

`Int64` 结构的 `MinValue` 属性或字段用于表示 `Int64` 的最小可能值。该字段的值为常量，意味着用户不能更改该字段的值。该字段的值为 **-9223372036854775808**。其十六进制值为 `0x8000000000000000`。

## 语法

```cs
public const long MinValue = -9223372036854775808;
```

## 返回值

该字段始终返回 `-9223372036854775808`。

## 示例

```cs
// C# program to illustrate the
// Int64.MinValue Field
using System;

class GFG {

    // Main Method
    static public void Main()
    {
        // display the Minimum
        // value of Int64 struct
        Console.WriteLine("Minimum Value is: " +
                           Int64.MinValue);

        // taking a variable
        long var1 = -2382373544;

        if(var1.Equals(Int64.MinValue))
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

## 输出

```cs
Minimum Value is: -9223372036854775808
Not equal..!!
Type of var1 is: Int64
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.int64.minvalue?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.int64.minvalue?view=netframework-4.7.2)