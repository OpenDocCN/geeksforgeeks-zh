# C# Type.GetTypeHandle() 方法

> 原文: [https://www.geeksforgeeks.org/c-sharp-type-gettypehandle-method/](https://www.geeksforgeeks.org/c-sharp-type-gettypehandle-method/)

`Type.GetTypeHandle()` 方法用于获取指定对象类型的句柄。

> **语法:** `public static RuntimeTypeHandle GetTypeHandle(object o);`
> 在这里，`o` 是需要为其获取类型句柄的对象。
>
> **返回值:** 该方法返回指定对象类型的句柄。
>
> **异常:** 如果 `o` 为 `null`，这个方法抛出 `ArgumentNullException`。

以下程序说明了 `Type.GetTypeHandle()` 方法的使用:

## 例 1:

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

### 输出:

```cs
Type referenced is System.RuntimeTypeHandle
```

## 例 2:

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

### 输出:

```cs
object is null.
Exception Thrown: System.ArgumentNullException
```

## 参考:

*   [https://docs.microsoft.com/en-us/dotnet/api/system.type.gettypehandle?view=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.type.gettypehandle?view=netframework-4.8)