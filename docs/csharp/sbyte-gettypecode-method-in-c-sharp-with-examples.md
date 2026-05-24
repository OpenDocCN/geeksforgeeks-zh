# SByte。C# 中的 GetTypeCode 方法及示例

> 原文:[https://www . geesforgeks . org/sbyte-gettypecode-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/sbyte-gettypecode-method-in-c-sharp-with-examples/)

**SByte。GetTypeCode** 方法用于获取值类型*的类型码*。

> **语法:**公共类型代码 gettype code()；
> 
> **返回值:**该方法返回枚举常量 SByte。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to illustrate the
// SByte.GetTypeCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Taking sbyte value
        sbyte s1 = 56;

        // Getting the typecode for SByte
        // using GetTypeCode() method
        TypeCode result = s1.GetTypeCode();

        // Display the TypeCode
        Console.WriteLine("TypeCode for SByte is: {0}",
                                               result);
    }
}
```

**Output:**

```cs
TypeCode for SByte is: SByte

```

**例 2:**

```cs
// C# program to illustrate the
// SByte.GetTypeCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // using result() Method
        result(SByte.MinValue);
        result(SByte.MaxValue);
    }

    // result() method
    public static void result(sbyte val)
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
TypeCode for -128 is SByte
TypeCode for 127 is SByte

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . sbyte . gettypecode？view=netcore-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.sbyte.gettypecode?view=netcore-2.1)