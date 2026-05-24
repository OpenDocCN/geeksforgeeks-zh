# UInt32。C# 中的 GetTypeCode 方法及示例

> 原文:[https://www . geeksforgeeks . org/uint 32-gettypecode-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/uint32-gettypecode-method-in-c-sharp-with-examples/)

**UInt32。GetTypeCode** 方法用于获取值类型 UInt32 的类型代码。

> **语法:**公共类型代码 gettype code()；
> 
> **返回值:**该方法返回枚举常量 UInt32。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to illustrate the
// UInt32.GetTypeCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Taking 32-bit unsigned integer 
        // i.e. UInt32
        uint s1 = 223;

        // Getting the typecode
        // using GetTypeCode() method
        TypeCode result = s1.GetTypeCode();

        // Display the TypeCode
        Console.WriteLine("TypeCode for UInt32 is: {0}",
                                                result);
    }
}
```

**Output:**

```cs
TypeCode for UInt32 is: UInt32

```

**例 2:**

```cs
// C# program to illustrate the
// UInt32.GetTypeCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // using result() Method
        result(UInt32.MinValue);
        result(UInt32.MaxValue);
    }

    // result() method
    public static void result(uint val)
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
TypeCode for 0 is UInt32
TypeCode for 4294967295 is UInt32

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . uint 32 . gettypecode？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uint32.gettypecode?view=netstandard-2.1)