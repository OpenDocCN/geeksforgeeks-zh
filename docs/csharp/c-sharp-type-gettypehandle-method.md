# C# |类型。GetTypeHandle()方法

> 原文:[https://www . geesforgeks . org/c-sharp-type-gettypehandle-method/](https://www.geeksforgeeks.org/c-sharp-type-gettypehandle-method/)

**类型。GetTypeHandle()方法**用于获取指定对象类型的句柄。

> **语法:**公共静态 RuntimeTypeHandle GetTypeHandle(对象 o)；
> 在这里，它需要为其获取类型句柄的对象。
> 
> **返回值:**该方法返回指定对象类型的句柄。
> 
> **异常**:如果 o 为空，这个方法抛出 **ArgumentNullException** 。

以下程序说明了*类型的使用。GetTypeHandle()* 方法:

**例 1:**

```cs
// C# program to demonstrate the
// Type.GetTypeHandle() Method
using System;
using System.Globalization;
using System.Reflection;

class GFG {

    // Main Method
    public static void Main()
    {

        // try-catch block for handling Exception
        try {

            // creating and initializing object Type
            Type type = typeof(int);

            // getting handle of given type
            // by using GetTypeHandle() Method
            RuntimeTypeHandle handle = Type.GetTypeHandle(type);

            // Display the Result
            Console.WriteLine("Type referenced is {0}", handle);
        }

        // catch ArgumentNullException here
        catch (ArgumentNullException e) 
        {
            Console.WriteLine("object is null.");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**输出:**

```cs
Type referenced is System.RuntimeTypeHandle

```

**例 2:**

```cs
// C# program to demonstrate the
// Type.GetTypeHandle() Method
using System;
using System.Globalization;
using System.Reflection;

class GFG {

    // Main Method
    public static void Main()
    {

        // try-catch block for handling Exception
        try {

            // creating and initializing object Type
            Type type = typeof(int);

            // getting handle of given type
            // by using GetTypeHandle() Method
            RuntimeTypeHandle handle = Type.GetTypeHandle(null);

            // Display the Result
            Console.WriteLine("Type referenced is {0}", handle);
        }

        // catch ArgumentNullException here
        catch (ArgumentNullException e)
        {
            Console.WriteLine("object is null.");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**输出:**

```cs
object is null.
Exception Thrown: System.ArgumentNullException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . type . gettypehandle？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.type.gettypehandle?view=netframework-4.8)