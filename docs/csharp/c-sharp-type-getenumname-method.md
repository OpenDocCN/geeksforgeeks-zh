# C# |类型。GetEnumName()方法

> 原文:[https://www . geesforgeks . org/c-sharp-type-getenumname-method/](https://www.geeksforgeeks.org/c-sharp-type-getenumname-method/)

**类型。GetEnumName(Object)方法**用于返回具有当前枚举类型指定值的常量的名称。

**语法:**

```cs
public virtual string GetEnumName (object value);
```

这里取*值*，取其名字进行检索。
**返回值:**该方法返回具有指定值的当前枚举类型成员的名称。如果没有找到这样的常数，那么它将返回 null。
**例外:**

*   **ArgumentException** :如果当前类型不是枚举或者值既不是当前类型，也没有与当前类型相同的基础类型。
*   **ArgumentNullException** :如果*值*为空。

下面的程序说明了上述方法的使用:
**例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate the
// Type.GetEnumName(Object) Method
using System;
using System.Globalization;
using System.Reflection;

class GFG {

    // Defining enum ABC
    enum ABC {A, B, C}

    // Main Method
    public static void Main()
    {

        // Creating try-catch block
        // to handle exceptions
        try {

            // Creating and initializing object
            // of ABC with instance of enum ABC
            ABC a = ABC.A;

            // Declaring and initializing
            // object of Type
            Type type = a.GetType();

            string obj = type.GetEnumName(a);

            Console.WriteLine("Name of constant is: " + obj);
        }

        // catch ArgumentNullException here
        catch (ArgumentNullException e)
        {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:** 

```cs
Name of constant is: A
```