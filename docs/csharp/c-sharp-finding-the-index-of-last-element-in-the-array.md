# C# |查找数组中最后一个元素的索引

> 原文:[https://www . geeksforgeeks . org/c-sharp-查找数组中最后一个元素的索引/](https://www.geeksforgeeks.org/c-sharp-finding-the-index-of-last-element-in-the-array/)

**GetUpperBound()方法**用于查找数组中指定维度的最后一个元素的索引。

**语法:**

```cs
public int GetUpperBound (int dimension);
```

这里*维*是需要确定上界的数组的从零开始的维。

**返回值:**该方法的返回类型为**系统。Int32** 。此方法返回数组中指定维度的最后一个元素的索引，如果指定维度为空，则返回-1。

**异常:**如果*维度*的值小于零，或者等于或大于[等级](https://docs.microsoft.com/en-us/dotnet/api/system.array.rank?view=netcore-2.1# System_Array_Rank)，该方法将给出*指数。*

**注意:*****getuperbound(0)***返回数组第一维的最后一个索引，**getuperbound(Rank–1)**返回数组最后一个维的最后一个索引。这个方法是一个 O(1)运算。

以下程序说明了 **GetUpperBound()方法**的使用:

**例 1:**

```cs
// C# program to illustrate the GetUpperBound(Int32)
// method in 1-D array
using System;

public class GFG {

    // Main method
    static public void Main()
    {

        // 1-D Array
        int[] value = {1, 2, 3, 4, 5, 6, 7};

        // Get the index of the last element
        // in the given Array by using 
        // GetUpperBound(Int32) method
        int myvalue = value.GetUpperBound(0);

        Console.WriteLine("Index: {0}", myvalue);
    }
}
```

**输出:**

```cs
Index: 6

```

**例 2:**

```cs
// C# program to find last index 
// value and rank of 2-D array
using System;

public class GFG {

    // Main method
    static public void Main()
    {

        // 2-D char Array
        char[, ] value = { { 'a', 'b' }, { 'c', 'd' }, 
                           { 'e', 'f' }, { 'g', 'h' },
                                       { 'i', 'j' } };

        // Get the index of the last element
        // and the rank of the given Array
        int myvalue = value.GetUpperBound(0);
        Console.WriteLine("Dimension: {0}", value.Rank);
        Console.WriteLine("Index: {0}", myvalue);
    }
}
```

**输出:**

```cs
Dimension: 2
Index: 4

```

**参考:**T2？view=netcore-2.1