# C# |类型。GetInterfaces()方法

> 原文:[https://www . geesforgeks . org/c-sharp-type-getinterfaces-method/](https://www.geeksforgeeks.org/c-sharp-type-getinterfaces-method/)

**类型。GetInterfaces()方法**用于在派生类中被重写时获取当前类型实现或继承的所有接口。

> **语法:**公共抽象类型[]GetInterfaces()；
> **返回值:**该方法返回一个 Type 对象数组，表示当前类型实现或继承的所有接口，如果当前类型没有实现或继承任何接口，则返回 Type 的空数组。

以下程序说明了**类型的使用。GetInterfaces()** 方法:

**例 1:**

## C#

```cs
// C# program to demonstrate the
// Type.GetInterfaces() Method
using System;
using System.Globalization;
using System.Reflection;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing object of Type
        Type objType = typeof(int);

        // Getting interface of specified name
        // using GetField(String) Method
        Type[] minterface = objType.GetInterfaces();

        // Display the Result
        Console.WriteLine("Interface present in type {0}", objType);
        for (int i = 0; i < minterface.Length; i++)
            Console.WriteLine(" {0}", minterface[i]);
    }
}
```

**Output:** 

```cs
Interface present in type System.Int32
 System.IFormattable
 System.IComparable
 System.IComparable`1[System.Int32]
 System.IConvertible
 System.IEquatable`1[System.Int32]
```