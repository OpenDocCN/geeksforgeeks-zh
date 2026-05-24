# C# |类型。GetEnumUnderlyingType()方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-type-getenumnderlyingtype-method/](https://www.geeksforgeeks.org/c-sharp-type-getenumunderlyingtype-method/)

**类型。GetEnumUnderlyingType()方法**用于返回当前枚举类型的底层类型。

**语法:**

```cs
public virtual Type GetEnumUnderlyingType ();
```

**返回值:**此方法返回当前枚举的基础类型。

**异常:**如果当前类型不是枚举或枚举类型无效(由于包含多个实例字段)，该方法将返回**参数异常**。

以下程序说明了上述方法的使用:

**例 1:**

## c#

```cs
// C# program to demonstrate the
// Type.GetEnumUnderlyingType() Method
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

            // Getting underlying type of current enumeration
            // By using GetEnumUnderlyingType() method
            Type obj = type.GetEnumUnderlyingType();

            // Display underlying type
            Console.Write("Underlying type is : {0} ", obj);
        }

        // ArgumentException here
        catch (ArgumentException e)
        {
            Console.Write("The current type is not an enumeration.");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**输出:**

```cs
Underlying type is : System.Int32
```

**例 2:** 为*ArgumentException*

## c#

```cs
// C# program to demonstrate the
// Type.GetEnumUnderlyingType() Method
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

            // Declaring and initializing
            // object of Type
            Type type = typeof(int);

            // Getting underlying type of current enumeration
            // By using GetEnumUnderlyingType() method
            Type obj = type.GetEnumUnderlyingType();

            // Display underlying type
            Console.Write("underlying type is : {0} ", obj);
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

**输出:**

```cs
The current type is not an enumeration.
Exception Thrown: System.ArgumentException
```

**参考:**

*   [https://docs。微软。com/en-us/dotnet/API/system。打字。getenumunderyingtype？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.type.getenumunderlyingtype?view=netframework-4.8)