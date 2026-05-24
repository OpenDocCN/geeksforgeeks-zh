# 数组的 C# | LongLength 属性

> 原文:[https://www . geeksforgeeks . org/c-sharp-long length-数组属性/](https://www.geeksforgeeks.org/c-sharp-longlength-property-of-an-array/)

**阵列。龙棱属性**用于获取一个 *64 位*整数，该整数表示[数组](https://www.geeksforgeeks.org/c-array-class/)所有维度中的元素总数。

**语法:**

```cs
public long LongLength { get; }
```

**属性值:**该属性返回一个 64 位整数，表示数组所有维度中的元素总数。

**示例:**

```cs
// C# program to illustrate the
// Array.LongLength Property
using System;
namespace geeksforgeeks {

class GFG {

    // Main Method
    public static void Main()
    {

        // Two-dimensional array
        int[, ] intarray = new int[, ] { { 1, 2 },
                                         { 3, 4 },
                                         { 5, 6 },
                                         { 7, 8 } };

        // The same array with dimensions
        // specified 4 row and 2 column.
        int[, ] intarray_d = new int[4, 2] { { 1, 2 }, 
                                             { 3, 4 }, 
                                             { 5, 6 }, 
                                             { 7, 8 } };

        Console.Write("Total Number of Elements in intarray: ");

        // using LongLength property
        Console.Write(intarray.LongLength);

        // getting the type of returned value
        Console.WriteLine("\nType of returned Length: " 
                  + (intarray.LongLength).GetType());

        // showing difference between Length
        // and LongLength property by getting
        // the type of the both property's
        // returned value

        Console.Write("\nTotal Number of Elements in intarray_d: ");

        // using Length property
        Console.Write(intarray_d.Length);

        // getting the type of returned value
        Console.WriteLine("\nType of returned Length: " 
                      + (intarray_d.Length).GetType());

        Console.Write("\nTotal Number of Elements in intarray_d: ");

        // using LongLengthLength property
        Console.Write(intarray_d.LongLength);

        // getting the type of returned value
        Console.WriteLine("\nType of returned Length: " 
                 + (intarray_d.LongLength).GetType());
    }
}
}
```

**Output:**

```cs
Total Number of Elements in intarray: 8
Type of returned Length: System.Int64

Total Number of Elements in intarray_d: 8
Type of returned Length: System.Int32

Total Number of Elements in intarray_d: 8
Type of returned Length: System.Int64

```

**注意:**在上面的程序中可以看到`Array.Length`属性总是返回类型*系统的长度。Int32* 但是`Array.LongLength` 属性总是返回类型*系统的长度。Int64* 。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . array . long length？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.array.longlength?view=netframework-4.7.2)