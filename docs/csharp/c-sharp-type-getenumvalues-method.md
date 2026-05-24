# C# |类型。GetEnumValues()方法

> 原文:[https://www . geesforgeks . org/c-sharp-type-getenumvalues-method/](https://www.geeksforgeeks.org/c-sharp-type-getenumvalues-method/)

**类型。GetEnumValues()方法**用于返回当前枚举类型中常量值的数组。
**语法:**

```cs
public virtual Array GetEnumValues ();
```

**返回值:**这个方法返回一个包含值的数组。数组的元素按二进制值排序，即枚举常数的无符号值。
**异常:**如果当前类型不是枚举，这个方法会给出 **ArgumentException** 。
以下程序说明了上述方法的使用:
**示例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate the
// Type.GetEnumValues() Method
using System;
using System.Globalization;
using System.Reflection;

class GFG {

    // Defining enum ABC
    enum ABC { A,
               B,
               C,
               D,
               E,
               F }

    // Main Method
    public static void Main()
    {

        // try-catch block to
        // handle exceptions
        try {

            // Creating and initializing object
            // of ABC with instance of enum ABC
            ABC a = ABC.A;

            // Declaring and initializing
            // object of Type
            Type type = a.GetType();

            // Getting an array of the values
            // of the constants
            // By using GetEnumValues() method
            Array obj = type.GetEnumValues();

            // Display values of the constants
            Console.Write("Values of the constants is : {0} ", obj);
        }

        // catch ArgumentException here
        catch (ArgumentException e)
        {
            Console.WriteLine("The current type is not an enumeration.");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:** 

```cs
Values of the constants is : GFG+ABC[] 
```

**示例 2:** 适用于*参数异常*

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate the
// Type.GetEnumValues() Method
using System;
using System.Globalization;
using System.Reflection;

class GFG {

    // Defining enum ABC
    enum ABC { A,
               B,
               C,
               D,
               E,
               F }

    // Main Method
    public static void Main()
    {

        // try-catch block to
        // handle exceptions
        try {

            // Creating and initializing object
            // of ABC with instance of enum ABC
            ABC a = ABC.A;

            // Declaring and initializing
            // object of Type
            Type type = typeof(int);

            // Getting an array of the values
            // of the constants
            // By using GetEnumValues() method
            Array obj = type.GetEnumValues();

            // Display values of the constants
            Console.Write("Values of the constants is : {0} ", obj);
        }

        // catch ArgumentException here
        catch (ArgumentException e)
        {
            Console.WriteLine("The current type is not an enumeration.");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:** 

```cs
The current type is not an enumeration.
Exception Thrown: System.ArgumentException
```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . type . getenumvalues？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.type.getenumvalues?view=netframework-4.8)