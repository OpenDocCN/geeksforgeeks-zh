# C# |类型。GetArrayRank()方法

> 原文:[https://www . geesforgeks . org/c-sharp-type-getarrayrank-method/](https://www.geeksforgeeks.org/c-sharp-type-getarrayrank-method/)

**类型。方法**用于获取一个[数组](https://www.geeksforgeeks.org/c-sharp-arrays/)中的维数。

> **语法:**public virtual int GetArrayRank()；
> **返回值:**该方法返回一个包含当前类型维数的整数。
> **异常:**如果当前类型不是数组，这个方法抛出 **ArgumentException** 。

以下程序说明了*类型的使用。【方法:
**例 1:*** 

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate the
// Type.GetArrayRank() Method
using System;
using System.Globalization;
using System.Reflection;

class GFG {

    // Main Method
    public static void Main()
    {

        try
        {
            // Declaring and initializing Type object
            Type type = typeof(int[,,,,, ]);

            // Getting the dimensions
            // using GetArrayRank()
            int rank = type.GetArrayRank();

            // Display the rank
            Console.WriteLine("ArrayRank is:  {0}", rank);
        }

        catch (ArgumentException e)
        {
            Console.WriteLine("The current type is not an Array");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:** 

```cs
ArrayRank is:  6
```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate the
// Type.GetArrayRank() Method
using System;
using System.Globalization;
using System.Reflection;

class GFG {

    // Main Method
    public static void Main()
    {

        try {

            // Declaring and initializing Type object
            Type type = typeof(int);

            // Getting ArrayRank by
            // using GetArrayRank()
            int rank = type.GetArrayRank();

            // Display the rank
            Console.WriteLine("ArrayRank is :  {0}", rank);
        }

        catch (ArgumentException e)
        {
            Console.WriteLine("The current type is not an Array");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:** 

```cs
The current type is not an Array
Exception Thrown: System.ArgumentException
```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . type . getarrayrank？view=netcore-3.0](https://docs.microsoft.com/en-us/dotnet/api/system.type.getarrayrank?view=netcore-3.0)