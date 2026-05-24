# Int32。C# 中的 GetTypeCode 方法及示例

> 原文:[https://www . geesforgeks . org/int 32-gettypecode-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/int32-gettypecode-method-in-c-sharp-with-examples/)

**Int32。GetTypeCode** 方法用于获取值类型 *Int32* 的类型代码。

> **语法:**公共类型代码 gettype code()；
> 
> **返回值:**该方法返回枚举常量 Int32。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to illustrate the
// Int32.GetTypeCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Taking int value
        // i.e. Int32
        int s1 = 3256;

        // Getting the typecode for Int32
        // using GetTypeCode() method
        TypeCode result = s1.GetTypeCode();

        // Display the TypeCode 
        Console.WriteLine("TypeCode for Int32 is: {0}",
                                               result);
    }
}
```

**Output:**

```cs
TypeCode for Int32 is: Int32

```

**例 2:**

```cs
// C# program to illustrate the
// Int32.GetTypeCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // using result() Method
        result(Int32.MinValue);
        result(Int32.MaxValue);
    }

    // result() method
    public static void result(int val)
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
TypeCode for -2147483648 is Int32
TypeCode for 2147483647 is Int32

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . int 32 . gettypecode？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.int32.gettypecode?view=netframework-4.7.2)