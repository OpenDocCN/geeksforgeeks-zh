# UInt16。C# 中的 GetTypeCode 方法及示例

> 原文:[https://www . geeksforgeeks . org/uint 16-gettypecode-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/uint16-gettypecode-method-in-c-sharp-with-examples/)

**UInt16。GetTypeCode** 方法用于获取值类型 UInt16 的类型代码。

> **语法:**公共类型代码 gettype code()；
> 
> **返回值:**该方法返回枚举常量 *UInt16* 。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to illustrate the
// UInt16.GetTypeCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Taking ushort value
        // i.e. UInt16
        ushort s1 = 223;

        // Getting the typecode
        // using GetTypeCode() method
        TypeCode result = s1.GetTypeCode();

        // Display the TypeCode
        Console.WriteLine("TypeCode for UInt16 is: {0}",
                                                result);
    }
}
```

**Output:**

```cs
TypeCode for UInt16 is: UInt16

```

**例 2:**

```cs
// C# program to illustrate the
// UInt16.GetTypeCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // using result() Method
        result(UInt16.MinValue);
        result(UInt16.MaxValue);
    }

    // result() method
    public static void result(ushort val)
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
TypeCode for 0 is UInt16
TypeCode for 65535 is UInt16

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . uint 16 . gettypecode？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uint16.gettypecode?view=netstandard-2.1)