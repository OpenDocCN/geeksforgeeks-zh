# C# | Char.GetTypeCode() 方法示例

> 原文：[https://www.geeksforgeeks.org/c-sharp-char-gettypecode-method-with-examples/](https://www.geeksforgeeks.org/c-sharp-char-gettypecode-method-with-examples/)

该方法用于返回值类型 `Char` 的*类型代码*。

**语法：**

```cs
public TypeCode GetTypeCode();
```

**返回值：** 这个方法返回枚举常量 `Char`。

下面的程序说明了 `Char.GetTypeCode()` 方法的使用：

## 示例 1

```cs
// C# program to demonstrate
// Char.GetTypeCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring val1 and val2
        char val1;
        bool val2;

        // initializing the
        // val1 and val2
        val1 = 'A';
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
TypeCode of val1 is Char
TypeCode of val2 is Boolean
```

## 示例 2

```cs
// C# program to demonstrate
// Char.GetTypeCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring val1 and val2
        char val1;
        float val2;

        // initializing the
        // val1 and val2
        val1 = 'a';
        val2 = 20f;

        // calling get() method
        get(val1);
        get(val2);
    }

    // Defining the get() method
    public static void get(char val)
    {
        // getting TypeCode
        // using GetTypeCode() method
        TypeCode t = val.GetTypeCode();

        // Display the TypeCode
        Console.WriteLine("TypeCode of {0} is {1}",
                          val, t);
    }

    public static void get(float val)
    {
        // getting TypeCode
        // using GetTypeCode() method
        TypeCode t = val.GetTypeCode();

        // Display the TypeCode
        Console.WriteLine("TypeCode of {0} is {1}",
                          val, t);
    }
}
```

**输出：**

```cs
TypeCode of a is Char
TypeCode of 20 is Single
```

**参考：**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.char.gettypecode?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.char.gettypecode?view=netframework-4.7.2)