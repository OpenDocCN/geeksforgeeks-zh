# Int64。C# 中的 GetTypeCode 方法及示例

> 原文:[https://www . geesforgeks . org/int 64-gettypecode-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/int64-gettypecode-method-in-c-sharp-with-examples/)

**Int64。GetTypeCode** 方法用于获取值类型 Int64 的类型代码。

> **语法:**公共类型代码 gettype code()；
> 
> **返回值:**该方法返回枚举常量 Int64。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to illustrate the
// Int64.GetTypeCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Taking long value
        // i.e. Int64
        long val = 4578123;

        // Getting the typecode for Int64
        // using GetTypeCode() method
        TypeCode result = val.GetTypeCode();

        // Display the TypeCode 
        Console.WriteLine("TypeCode for Int64 is: {0}",
                                               result);
    }
}
```

**Output:**

```cs
TypeCode for Int64 is: Int64

```

**例 2:**

```cs
// C# program to illustrate the
// Int64.GetTypeCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // using result() Method
        result(Int64.MinValue);
        result(Int64.MaxValue);
    }

    // result() method
    public static void result(long val)
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
TypeCode for -9223372036854775808 is Int64
TypeCode for 9223372036854775807 is Int64

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . int 64 . gettypecode？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.int64.gettypecode?view=netframework-4.7.2)