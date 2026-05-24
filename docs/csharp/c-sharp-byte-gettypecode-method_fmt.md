# C# | Byte.GetTypeCode() 方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-byte-gettypecode-method/](https://www.geeksforgeeks.org/c-sharp-byte-gettypecode-method/)

此方法用于返回值类型 `Byte` 的类型代码。

**语法：**

```cs
public TypeCode GetTypeCode();
```

**返回值：** 返回枚举常量 `Byte`。

以下程序说明了 `Byte.GetTypeCode()` 方法的使用：

**示例 1：**

```cs
// C# program to demonstrate
// Byte.GetTypeCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declaring val1 and val2
        byte val1;
        bool val2;

        // initializing the
        // val1 and val2
        val1 = 12;
        val2 = true;

        // getting TypeCode
        // using GetTypeCode() method
        TypeCode t1 = val1.GetTypeCode();
        TypeCode t2 = val2.GetTypeCode();

        // Display TypeCode
        Console.WriteLine("TypeCode of val1 is {0}", t1);
        Console.WriteLine("TypeCode of val2 is {0}", t2);
    }
}
```

**输出：**

```cs
TypeCode of val1 is Byte
TypeCode of val2 is Boolean
```

**示例 2：**

```cs
// C# program to demonstrate
// Byte.GetTypeCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declaring val1 and val2
        byte val1;
        bool val2;

        // initializing the
        // val1 and val2
        val1 = 12;
        val2 = true;

        // calling get() method
        get(val1);
        get(val2);
    }

    // Defining the get() method
    public static void get(byte val)
    {

        // getting TypeCode
        // using GetTypeCode() method
        TypeCode t = val.GetTypeCode();

        // Display the TypeCode
        Console.WriteLine("TypeCode of {0} is {1}", val, t);
    }

    public static void get(bool val)
    {

        // getting TypeCode
        // using GetTypeCode() method
        TypeCode t = val.GetTypeCode();

        // Display the TypeCode
        Console.WriteLine("TypeCode of {0} is {1}", val, t);
    }
}
```

**输出：**

```cs
TypeCode of 12 is Byte
TypeCode of True is Boolean
```

**参考：**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.byte.gettypecode?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.byte.gettypecode?view=netframework-4.7.2)