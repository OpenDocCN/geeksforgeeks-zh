# C# |如何获取类字符串的类型代码

> 原文:[https://www . geesforgeks . org/c-sharp-如何获取类字符串的类型代码/](https://www.geeksforgeeks.org/c-sharp-how-to-get-typecode-for-the-class-string/)

**GetTypeCode()方法**用于获取指定字符串的 **[TypeCode](https://docs.microsoft.com/en-us/dotnet/api/system.typecode?view=netframework-4.7.2)** 。
这里 TypeCode 枚举代表一种特定类型的对象。在类型代码中，每种数据类型都由一个特定的数字表示，比如字符串由 18 表示，Int32 由 9 表示，等等。

**语法:**

```cs
public TypeCode GetTypeCode ();
```

**返回值:**这个方法返回一个枚举常量。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# program to illustrate the 
// GetTypeCode() Method
using System;

class GFG {

    // Main method
    public static void Main()
    {

        // variables
        string str1 = "Geeksforgeeks";
        int a = 12;

        // get the TypeCode by
        // using GetTypeCode() method
        Console.WriteLine("The TypeCode for {0}': {1}",
                              str1, str1.GetTypeCode());

        Console.WriteLine("The TypeCode for '{0}': {1}",
                                    a, a.GetTypeCode());
    }
}
```

**输出:**

```cs
The TypeCode for Geeksforgeeks': String
The TypeCode for '12': Int32

```

**例 2:**

```cs
// C# program to illustrate the 
// GetTypeCode() Method
using System;

class GFG {

// Main method
public static void Main()
{
    // given string
    String str1 = "Geeks";

    // get the TypeCode of the given String
    // using GetTypeCode() method
    TypeCode g = str1.GetTypeCode();
    Console.WriteLine("TypeCode for '{0}': {1}, Which means it represents a {2}.",
                                          str1, g.ToString("D"), g.ToString("F"));
}
}
```

**输出:**

```cs
TypeCode for 'Geeks': 18, Which means it represents a String.
```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . string . gettypecode？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.string.gettypecode?view=netframework-4.7.2)