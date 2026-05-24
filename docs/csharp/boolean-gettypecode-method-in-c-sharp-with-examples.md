# 布尔。C# 中的 GetTypeCode 方法及示例

> 原文:[https://www . geesforgeks . org/boolean-gettypecode-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/boolean-gettypecode-method-in-c-sharp-with-examples/)

**布尔。GetTypeCode** 方法用于获取值类型*布尔*的类型代码。

> **语法:**公共类型代码 gettype code()；
> 
> **返回值:**该方法返回枚举常量*布尔*。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to illustrate the
// Boolean.GetTypeCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Taking a Boolean value
        bool s1 = true;

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
TypeCode for True is: Boolean

```

**例 2:**

```cs
// C# program to illustrate the
// Boolean.GetTypeCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // using result() Method
        result(true);
        result(false);
    }

    // result() method
    public static void result(bool val)
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
TypeCode for True is Boolean
TypeCode for False is Boolean

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . boolean . gettypecode？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.boolean.gettypecode?view=netframework-4.8)