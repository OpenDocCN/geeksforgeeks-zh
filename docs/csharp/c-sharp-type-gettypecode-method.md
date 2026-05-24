# C# |类型。GetTypeCode()方法

> 原文:[https://www . geesforgeks . org/c-sharp-type-gettypecode-method/](https://www.geeksforgeeks.org/c-sharp-type-gettypecode-method/)

**类型。GetTypeCode()方法**用于获取指定类型的底层类型代码。

> **语法:**公共静态 TypeCode GetTypeCode(类型类型)；
> 在这里，它需要获取其底层类型代码的类型。
> 
> **返回值:**该方法返回基础类型的代码，如果类型为空，则返回空。

以下程序说明了*类型的使用。GetTypeCode()* 方法:

**例 1:**

```cs
// C# program to demonstrate the
// Type.GetTypeCode() Method
using System;
using System.Globalization;
using System.Reflection;

class GFG {

    // Main Method
    public static void Main()
    {

        // creating and initializing object Type
        Type type = typeof(int);

        // Getting the TypeCode
        TypeCode code = Type.GetTypeCode(type);

        // Display the Result
        Console.WriteLine("TypeCode is {0}", code);
    }
}
```

**Output:**

```cs
TypeCode is Int32

```

**例 2:**

```cs
// C# program to demonstrate the
// Type.GetTypeCode() Method
using System;
using System.Globalization;
using System.Reflection;

class GFG {

    // Main Method
    public static void Main()
    {
        // Calling get() Method
        get(typeof(int));
        get(typeof(decimal));
        get(typeof(double));
        get(typeof(short));
        get(typeof(string));
    }

    // defining get Method
    public static void get(Type type)
    {

        // Getting Typecode
        TypeCode code = Type.GetTypeCode(type);

        // Display the Result
        Console.WriteLine("TypeCode of {1} is {0}", code, type);
    }
}
```

**Output:**

```cs
TypeCode of System.Int32 is Int32
TypeCode of System.Decimal is Decimal
TypeCode of System.Double is Double
TypeCode of System.Int16 is Int16
TypeCode of System.String is String

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . type . gettypecode？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.type.gettypecode?view=netframework-4.8)