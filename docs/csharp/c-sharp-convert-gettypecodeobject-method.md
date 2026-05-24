# C# | Convert。获取类型代码(对象)方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-convert-gettypecodeobject-method/](https://www.geeksforgeeks.org/c-sharp-convert-gettypecodeobject-method/)

该方法用于返回指定对象的*类型代码*。
**语法:**

```cs
public static TypeCode GetTypeCode (object value);
```

这里*值*是实现*图标可转换*界面的对象。
**返回值:**该方法返回*类型码*为值，如果*值*为*空*，则*为空。
以下程序说明了**转换的使用。GetTypeCode(Object)** 方法:
**示例 1:***

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// Convert.GetTypeCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declaring val1 and val2
        string val1;
        bool val2;

        // initializing the
        // val1 and val2
        val1 = "abab";
        val2 = true;

        // getting TypeCode
        // using Convert.GetTypeCode() method
        TypeCode t1 = Convert.GetTypeCode(val1);
        TypeCode t2 = Convert.GetTypeCode(val2);

        // Display TypeCode
        Console.WriteLine("TypeCode of val1 is {0}", t1);
        Console.WriteLine("TypeCode of val2 is {0}", t2);
    }
}
```

**Output:** 

```cs
TypeCode of val1 is String
TypeCode of val2 is Boolean
```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// Convert.GetTypeCode() Method
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
        // using Convert.GetTypeCode() method
        TypeCode t = Convert.GetTypeCode(val);

        // Display the TypeCode
        Console.WriteLine("TypeCode of {0}"+
                         " is {1}", val, t);
    }
    public static void get(float val)
    {

        // getting TypeCode
        // using GetTypeCode() method
        TypeCode t = Convert.GetTypeCode(val);

        // Display the TypeCode
        Console.WriteLine("TypeCode of {0}"+
                         " is {1}", val, t);
    }
}
```

**Output:** 

```cs
TypeCode of a is Char
TypeCode of 20 is Single
```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . convert . gettypecode？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.convert.gettypecode?view=netframework-4.7.2)