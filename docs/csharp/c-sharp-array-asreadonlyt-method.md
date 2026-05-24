# C# |数组。AsReadOnly(T[])方法

> 原文:[https://www . geesforgeks . org/c-sharp-array-as readonly t-method/](https://www.geeksforgeeks.org/c-sharp-array-asreadonlyt-method/)

此方法用于返回指定数组的只读包装。

**语法:**

```cs
public static System.Collections.ObjectModel.
ReadOnlyCollection<T> AsReadOnly<T> (T[] array);
```

这里，T 是数组元素的类型。

**返回值:**该方法返回只读的*[readonly collection<T>](https://docs.microsoft.com/en-us/dotnet/api/system.collections.objectmodel.readonlycollection-1?view=netframework-4.7.2)*包装器。

**异常:**如果数组为空，这个方法抛出 **ArgumentNullException** 。

下面是举例说明**数组。AsReadOnly(T[])方法:**

**例 1:**

```cs
// C# program to demonstrate
// AsReadOnly() method
using System;
using System.Collections.Generic;

public class GFG {

    // Main Method
    public static void Main()
    {

        // Creating and initializing new the String
        String[] myArr = {"Sun", "Mon", "Tue", "Thu"};

        // Display the values of the myArr.
        Console.WriteLine("Initial Array:");

        // calling the PrintIndexAndValues() 
        // method to print
        PrintIndexAndValues(myArr);

        // Create a read-only IList 
        // wrapper around the array.
        IList<String> myList = Array.AsReadOnly(myArr);

        // Display the values of the read-only myList.
        Console.WriteLine("Read-only Array: ");

        // calling the PrintIndexAndValues() 
        // method to print
        PrintIndexAndValues(myList);
    }

    // Defining the method 
    // PrintIndexAndValues
    public static void PrintIndexAndValues(String[] myArr)
    {
        for (int i = 0; i < myArr.Length; i++) {

            Console.WriteLine("{0}", myArr[i]);
        }
        Console.WriteLine();
    }

    // Defining the method 
    // PrintIndexAndValues 
    public static void PrintIndexAndValues(IList<String> myList)
    {
        for (int i = 0; i < myList.Count; i++) {
            Console.WriteLine("{0}", myList[i]);
        }
    }
}
```

**输出:**

```cs
Initial Array:
Sun
Mon
Tue
Thu

Read-only Array: 
Sun
Mon
Tue
Thu

```

**例 2:**

```cs
// C# program to demonstrate
// AsReadOnly() method
// For ArgumentNullException
using System;
using System.Collections.Generic;

public class GFG {

    // Main Method
    public static void Main()
    {

        try {

            // Creating and initializing new
            // the String with a null value
            String[] myArr = null;

            // Create a read-only IList 
            // wrapper around the array.
            IList<String> myList = Array.AsReadOnly(myArr);

            // Display the values of 
            // the read-only myList.
            Console.WriteLine("Read-only Array:");

            // calling the PrintIndexAndValues()
            // method to print
            PrintIndexAndValues(myList);
        }
        catch (ArgumentNullException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining the method PrintIndexAndValues 
    public static void PrintIndexAndValues(String[] myArr)
    {
        for (int i = 0; i < myArr.Length; i++) {
            Console.WriteLine("{0}", myArr[i]);
        }
        Console.WriteLine();
    }

    // Defining the method PrintIndexAndValues 
    public static void PrintIndexAndValues(IList<String> myList)
    {
        for (int i = 0; i < myList.Count; i++) {
            Console.WriteLine("{0}", myList[i]);
        }
    }
}
```

**输出:**

```cs
Exception Thrown: System.ArgumentNullException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . array . as readonly？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.array.asreadonly?view=netframework-4.7.2)