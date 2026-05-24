# C# |类型。GetEnumNames()方法

> 原文:[https://www . geesforgeks . org/c-sharp-type-getenumnames-method/](https://www.geeksforgeeks.org/c-sharp-type-getenumnames-method/)

**类型。GetEnumNames()方法**用于返回当前枚举类型成员的名称。

**语法:**

```cs
public virtual string[] GetEnumNames ();
```

**返回:**这个方法返回一个包含枚举成员名称的数组。
**异常:**如果当前类型不是枚举，这个方法会给出 **ArgumentException** 。

以下程序说明了上述方法的使用:

**例 1:**

## C#

```cs
// C# program to demonstrate the
// Type.GetEnumNames(Object) Method
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

            // Getting Array of constants
            // By using GetEnumNames() method
            string[] obj = type.GetEnumNames();

            // Display Array obj
            Console.WriteLine("The constants are as follow :-");
            for (int i = 0; i < obj.Length; i++)
                Console.Write("{0} ", obj[i]);
        }

        // catch ArgumentException here
        catch (ArgumentException e)
        {
            Console.Write("The current type is not an enumeration.");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:** 

```cs
The constants are as follow :-
A B C D E F
```

**示例 2:** 适用于*参数异常*

## C#

```cs
// C# program to demonstrate the
// Type.GetEnumNames(Object) Method
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

        // Creating try-catch block
        // to handle exceptions
        try {

            // Declaring and initializing
            // object of Type
            Type type = typeof(int);

            // Getting Array of constants
            // By using GetEnumNames() method
            string[] obj = type.GetEnumNames();

            // Display Array obj
            Console.WriteLine("The constants are as follow :-");
            for (int i = 0; i < obj.Length; i++)
                Console.Write("{0} ", obj[i]);
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

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . type . getenumnames？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.type.getenumnames?view=netframework-4.8)