# C# |类型。GetTypeFromHandle()方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-type-gettypefromchandle-method/](https://www.geeksforgeeks.org/c-sharp-type-gettypefromhandle-method/)

**类型。GetTypeFromHandle()方法**用于获取指定类型句柄引用的类型。

> **语法:**公共静态类型 GetTypeFromHandle(RuntimeTypeHandle 句柄)；
> 这里取指类型的宾语。
> 
> **返回值:**该方法返回指定 RuntimeTypeHandle 引用的类型，如果句柄的 Value 属性为空，则返回 null。

以下程序说明了*类型的使用。GetTypeFromHandle()* 方法:

**例 1:**

```cs
// C# program to demonstrate the
// Type.GetTypeFromHandle() Method
using System;
using System.Globalization;
using System.Reflection;

class GFG {

    // Main Method
    public static void Main()
    {

        // creating and initializing object Type
        Type type = typeof(int);

        // creating object of RuntimeTypeHandle 
        // and getting instance of type
        RuntimeTypeHandle handle = Type.GetTypeHandle(type);

        // Getting the type referenced by
        // the specified RuntimeTypeHandle,
        // using GetTypeFromHandle() Method
        Type outtype = Type.GetTypeFromHandle(handle);

        // Display the Result
        Console.WriteLine("Type referenced is {0}", outtype);
        Console.WriteLine("Attributes are: " + outtype.Attributes);
    }
}
```

**Output:**

```cs
Type referenced is System.RuntimeType
Attributes are: AutoLayout, AnsiClass, Class, SequentialLayout, Serializable, BeforeFieldInit

```

**例 2:**

```cs
// C# program to demonstrate the
// Type.GetTypeFromHandle() Method
using System;
using System.Globalization;
using System.Reflection;

// Defining Empty struct
struct Empty {}

class GFG {

    // Main Method
    public static void Main()
    {

        // creating and initializing object Type
        Type type = typeof(Empty);

        // creating object of RuntimeTypeHandle 
        // and getting instance of type
        RuntimeTypeHandle handle = Type.GetTypeHandle(type);

        // Getting the type referenced by
        // the specified RuntimeTypeHandle,
        // using GetTypeFromHandle() Method
        Type outtype = Type.GetTypeFromHandle(handle);

        // Display the Result
        Console.WriteLine("Type referenced is {0}", outtype);
        Console.WriteLine("Attributes are: " + outtype.Attributes);
    }
}
```

**Output:**

```cs
Type referenced is System.RuntimeType
Attributes are: AutoLayout, AnsiClass, Class, SequentialLayout, Serializable, BeforeFieldInit

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . type . gettypefromchandle？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.type.gettypefromhandle?view=netframework-4.8)