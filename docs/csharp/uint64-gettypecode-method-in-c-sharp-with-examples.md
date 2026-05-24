# UInt64。C# 中的 GetTypeCode 方法及示例

> 原文:[https://www . geeksforgeeks . org/uint 64-gettypecode-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/uint64-gettypecode-method-in-c-sharp-with-examples/)

**UInt64。GetTypeCode** 方法用于获取值类型 UInt64 的类型代码。

> **语法:**公共类型代码 gettype code()；
> 
> **返回值:**该方法返回枚举常量 UInt64。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to illustrate the
// UInt64.GetTypeCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Taking 64-bit unsigned 
        // long value i.e. UInt64
        ulong s1 = 134851223;

        // Getting the typecode for UInt64
        // using GetTypeCode() method
        TypeCode result = s1.GetTypeCode();

        // Display the TypeCode
        Console.WriteLine("TypeCode for UInt64 is: {0}",
                                                result);
    }
}
```

**Output:**

```cs
TypeCode for UInt64 is: UInt64

```

**例 2:**

```cs
// C# program to illustrate the
// UInt64.GetTypeCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // using result() Method
        result(UInt64.MinValue);
        result(UInt64.MaxValue);
    }

    // result() method
    public static void result(ulong val)
    {

        // using GetTypeCode() method
        TypeCode code = val.GetTypeCode();

        // Display the TypeCode
        Console.WriteLine("TypeCode for {0} is {1}",
                                         val, code);
    }
}
```

**Output:**

```cs
TypeCode for 0 is UInt64
TypeCode for 18446744073709551615 is UInt64

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . uint 64 . gettypecode？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uint64.gettypecode?view=netstandard-2.1)