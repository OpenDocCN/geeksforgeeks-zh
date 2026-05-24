# 翻倍。C# 中的 GetTypeCode()方法

> 原文:[https://www . geesforgeks . org/double-gettypecode-method-in-c-sharp/](https://www.geeksforgeeks.org/double-gettypecode-method-in-c-sharp/)

**翻倍。GetTypeCode()方法**用于返回值类型 Double 的类型代码。

> **语法:**公共类型代码 gettype code()；
> 
> **返回值:**该方法返回枚举常量 Double。

下面的程序说明了 *Double 的使用。GetTypeCode()* 方法:

**例 1:**

```cs
// C# program to demonstrate the
// Double.GetTypeCode()
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declaring and initializing value1
        double value1 = 10d;

        // getting the typeCode
        // using GetTypeCode() method
        TypeCode value = value1.GetTypeCode();

        // Display the TypeCode
        Console.WriteLine("TypeCode is {0}", value);
    }
}
```

**Output:**

```cs
TypeCode is Double

```

**例 2:**

```cs
// C# program to demonstrate the
// Double.GetTypeCode()
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // calling get() method
        get(5d);
        get(5.5d);
        get(10d);
        get(7.5d);
    }

    // defining get() method
    public static void get(double value1)
    {

        // getting the TypeCode
        // using GetTypeCode() method
        TypeCode value = value1.GetTypeCode();

        // Display the TypeCode
        Console.WriteLine("TypeCode is {0}", value);
    }
}
```

**Output:**

```cs
TypeCode is Double
TypeCode is Double
TypeCode is Double
TypeCode is Double

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . double . gettypecode？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.double.gettypecode?view=netframework-4.7.2)