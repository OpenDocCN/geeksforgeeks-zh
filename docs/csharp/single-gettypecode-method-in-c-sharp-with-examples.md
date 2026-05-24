# 单身。C# 中的 GetTypeCode 方法及示例

> 原文:[https://www . geesforgeks . org/single-gettypecode-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/single-gettypecode-method-in-c-sharp-with-examples/)

**单身。获取类型代码**方法用于获取值类型*单*的类型代码。

> **语法:**公共类型代码 gettype code()；
> 
> **返回值:**该方法返回枚举常量*单个*。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to illustrate the
// Single.GetTypeCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Taking sbyte value
        float s1 = 56;

        // Getting the typecode
        // using GetTypeCode() method
        TypeCode result = s1.GetTypeCode();

        // Display the TypeCode
        Console.WriteLine("TypeCode for {0} is: {1}",
                                         s1, result);
    }
}
```

**Output:**

```cs
TypeCode for 56 is: Single

```

**例 2:**

```cs
// C# program to illustrate the
// Single.GetTypeCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // using result() Method
        result(Single.MinValue);
        result(Single.MaxValue);
    }

    // result() method
    public static void result(float val)
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
TypeCode for -3.402823E+38 is Single
TypeCode for 3.402823E+38 is Single

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . single . gettypecode？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.single.gettypecode?view=netstandard-2.1)