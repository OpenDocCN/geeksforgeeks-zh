# C# |类型。GetTypeArray()方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-type-gettypelarray-method/](https://www.geeksforgeeks.org/c-sharp-type-gettypearray-method/)

**类型。GetTypeArray()方法**用于获取指定数组中对象的类型。

> **语法:**公共静态类型[] GetTypeArray(对象[]args)；
> 这里，需要一个对象数组来确定对象的类型。
> 
> **返回值:**这个方法返回一个 Type 对象的数组，表示 args 中对应元素的类型。
> 
> **异常**:如果*参数*为空或者*参数*中的一个或多个元素为空，则该方法抛出**参数异常**。

以下程序说明了*类型的使用。gettypelarray()*方法:

**例 1:**

```cs
// C# program to demonstrate the
// Type.GetTypeArray(Object[]) Method
using System;
using System.Globalization;
using System.Reflection;

// Defining class Empty
public class Empty { }

class GFG {

    // Main Method
    public static void Main()
    {

        // try-catch block for handling Exception
        try {

            // creating and initializing object
            object[] obj = {2, 3.4, 'c', "ram"};

            // using GetProperties() Method
            Type[] type = Type.GetTypeArray(obj);

            // Display the Result
            Console.WriteLine("Types of the objects in the specified array: ");
            for (int i = 0; i < type.Length; i++)
                Console.WriteLine(" {0}", type[i]);
        }

        // catch ArgumentNullException here
        catch (ArgumentNullException e)
        {
            Console.Write("One or more of the elements in args is null.");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
Types of the objects in the specified array: 
 System.Int32
 System.Double
 System.Char
 System.String

```

**例 2:**

```cs
// C# program to demonstrate the
// Type.GetTypeArray(Object[]) Method
using System;
using System.Globalization;
using System.Reflection;

// Defining class Empty
public class Empty {}

class GFG {

    // Main Method
    public static void Main()
    {

        // try-catch block for handling Exception
        try {

            // creating and initializing object
            object[] obj = {2, 3.4, 'c', "ram", null};

            // using GetProperties() Method
            Type[] type = Type.GetTypeArray(obj);

            // Display the Result
            Console.WriteLine("Types of the objects in the specified array: ");
            for (int i = 0; i < type.Length; i++)
                Console.WriteLine(" {0}", type[i]);
        }

        // catch ArgumentNullException here
        catch (ArgumentNullException e) 
        {
            Console.WriteLine("One or more of the elements in args is null.");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
One or more of the elements in args is null.
Exception Thrown: System.ArgumentNullException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . type . gettypelarray？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.type.gettypearray?view=netframework-4.8)