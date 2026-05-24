# 如何在 C# 中找到数组的长度

> 原文:[https://www . geeksforgeeks . org/如何找到 c-sharp 中的数组长度/](https://www.geeksforgeeks.org/how-to-find-the-length-of-an-array-in-c-sharp/)

**阵列。长度属性**用于获取数组所有维度的元素总数。基本上，数组的长度是该数组所有维度所包含的元素总数。

**语法:**

```cs
public int Length { get; }
```

**属性值:**该属性返回数组所有维度的元素总数。如果数组中没有元素，它也可以返回零。返回类型为`System.Int32`。

**异常:**如果数组是多维的，并且包含的元素不止 **`MaxValue`** 个，则该属性抛出***overowexception***。这里 MaxValue 是 2147483647。

以下程序说明了上述属性的使用:

**例 1:**

```cs
// C# program to find the
// the total number of
// elements in 1-D Array
using System;
namespace geeksforgeeks {

class GFG {

    // Main Method
    public static void Main()
    {

        // declares a 1D Array of string.
        string[] weekDays;

        // allocating memory for days.
        weekDays = new string[] {"Sun", "Mon", "Tue", "Wed",
                                       "Thu", "Fri", "Sat"};

        // Displaying Elements of the array
        foreach(string day in weekDays)
            Console.Write(day + " ");

        Console.Write("\nTotal Number of Elements: ");

        // using Length property
        Console.Write(weekDays.Length);
    }
}
}
```

**Output:**

```cs
Sun Mon Tue Wed Thu Fri Sat 
Total Number of Elements: 7

```

**例 2:**

```cs
// C# program to find the total
// number of elements in the
// multidimensional Arrays
using System;
namespace geeksforgeeks {

class GFG {

    // Main Method
    public static void Main()
    {

        // Two-dimensional array
        int[, ] intarray = new int[, ] {{1, 2},
                                        {3, 4},
                                        {5, 6},
                                        {7, 8}};

        // The same array with dimensions
        // specified 4 row and 2 column.
        int[, ] intarray_d = new int[4, 2] {{ 1, 2}, 
                                             {3, 4}, 
                                             {5, 6},
                                             {7, 8}};

        // Three-dimensional array.
        int[,, ] intarray3D = new int[,, ] {{{ 1, 2, 3},
                                            { 4, 5, 6}},
                                            {{ 7, 8, 9},
                                         {10, 11, 12}}};

        // The same array with dimensions
        // specified 2, 2 and 3.
        int[,, ] intarray3Dd = new int[2, 2, 3] {{{1, 2, 3},
                                                 {4, 5, 6}},
                                                 {{ 7, 8, 9},
                                              {10, 11, 12}}};

        Console.Write("Total Number of Elements in intarray: ");

        // using Length property
        Console.Write(intarray.Length);

        Console.Write("\nTotal Number of Elements in intarray_d: ");

        // using Length property
        Console.Write(intarray_d.Length);

        Console.Write("\nTotal Number of Elements in intarray3D: ");

        // using Length property
        Console.Write(intarray3D.Length);

        Console.Write("\nTotal Number of Elements in intarray3Dd: ");

        // using Length property
        Console.Write(intarray3Dd.Length);
    }
}
}
```

**Output:**

```cs
Total Number of Elements in intarray: 8
Total Number of Elements in intarray_d: 8
Total Number of Elements in intarray3D: 12
Total Number of Elements in intarray3Dd: 12

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . array . length？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.array.length?view=netframework-4.7.2)