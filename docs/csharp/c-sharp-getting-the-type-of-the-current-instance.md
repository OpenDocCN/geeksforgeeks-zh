# C# |获取当前实例的类型

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-type-of-current-instance/](https://www.geeksforgeeks.org/c-sharp-getting-the-type-of-the-current-instance/)

**物体。GetType 方法**用于查找当前实例的类型。此方法返回用于考虑的类型类的实例。

**语法:**

```cs
public Type GetType ();
```

**返回值:**该方法返回当前实例的确切运行时类型。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# program to illustrate the 
// GetType() method
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // string type
        string str1 = "GFG";
        string str2 = "5";

        // using GetType() method
        Console.WriteLine("Type of str1: " +str1.GetType());
        Console.WriteLine("Type of str2: " +str2.GetType());
    }
}
```

**输出:**

```cs
Type of str1: System.String
Type of str2: System.String

```

**例 2:**

```cs
// C# program to illustrate the 
// GetType() method
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Variables
        string str1 = "C#";
        string str2 = "DSA";
        int str3 = 43;

        // Display the given string and their type
        // using GetType() method
        Console.WriteLine("Str 1 is : {0}", str1);
        Console.WriteLine("Str 2 is : {0}", str2);
        Console.WriteLine("Str 3 is : {0}", str3);

        // Check the given str1, str2,
        // and str3 are of same type or not
        // using GetType() method
        Console.WriteLine("Is Str 1 and Str 2 of same type? : {0}", 
            Object.ReferenceEquals(str1.GetType(), str2.GetType()));

        Console.WriteLine("Is Str 2 and Str 3 of same type? : {0}",
           Object.ReferenceEquals(str2.GetType(), str3.GetType()));

        Console.WriteLine("Is Str 3 and Str 2 of same type? : {0}", 
           Object.ReferenceEquals(str3.GetType(), str2.GetType()));
    }
}
```

**输出:**

```cs
Str 1 is : C#
Str 2 is : DSA
Str 3 is : 43
Is Str 1 and Str 2 of same type? : True
Is Str 2 and Str 3 of same type? : False
Is Str 3 and Str 2 of same type? : False

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . object . gettype？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.object.gettype?view=netframework-4.7.2)