# C# | Type.GetTypeCode() 方法

> 原文: [https://www.geeksforgeeks.org/c-sharp-type-gettypecode-method/](https://www.geeksforgeeks.org/c-sharp-type-gettypecode-method/)

`Type.GetTypeCode()` 方法用于获取指定类型的底层类型代码。

## 语法

```csharp
public static TypeCode GetTypeCode(Type type);
```

这里，`type` 参数是需要获取其底层类型代码的类型。

## 返回值

该方法返回基础类型的代码，如果类型为 `null`，则返回 `null`。

## 示例

以下程序说明了 `Type.GetTypeCode()` 方法的使用：

### 示例 1

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

**输出:**

```cs
TypeCode is Int32
```

### 示例 2

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

**输出:**

```cs
TypeCode of System.Int32 is Int32
TypeCode of System.Decimal is Decimal
TypeCode of System.Double is Double
TypeCode of System.Int16 is Int16
TypeCode of System.String is String
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.type.gettypecode?view=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.type.gettypecode?view=netframework-4.8)