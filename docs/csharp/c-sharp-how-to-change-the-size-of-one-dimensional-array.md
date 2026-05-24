# C#|如何改变一维数组的大小

> 原文:[https://www . geeksforgeeks . org/c-sharp-如何改变一维数组的大小/](https://www.geeksforgeeks.org/c-sharp-how-to-change-the-size-of-one-dimensional-array/)

**阵列。Resize(T[]，Int32)方法**用于调整数组中元素数量的大小。或者换句话说，此方法用于将一维数组的元素数量更改为指定的新大小。它只调整一维数组的大小，不调整多维数组的大小。

**语法:**

```cs
public static void Resize<T> (ref T[] array, int newSize);
```

**参数:**

> **数组:**它是一维的，从零开始调整大小的数组，或者为 null 创建一个指定大小的新数组。
> **纽泽西:**正是新阵的规模。

**异常:**如果 *nsize* 的值小于零，那么这个方法会给出*argumentout of range Exception*。

**注:**此方法为 O(n)运算，其中 n 为新大小。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# program to resize the
// elements of the 1-D array
using System;

public class GFG {

    // Main method
    static public void Main()
    {

        // create and initialize array
        string[] myarray = {"C#", "Java", "C++", "Python",
                             "HTML", "CSS", "JavaScript"};

        // Display original array before Resize
        Console.WriteLine("Original Array:");

        foreach(string i in myarray)
        {
            Console.WriteLine(i);
        }

        int len = myarray.Length;
        Console.WriteLine("Length of myarray: "+len);
        Console.WriteLine();

        // Resize the element of myarray and 
        // create a new array. Here new array
        // is smaller than the original array 
        // so, elements are copied from the 
        // myarray to the new array until the
        // new one is filled. The rest of the
        // elements in the old array are ignored
        Array.Resize(ref myarray, len - 3);

        Console.WriteLine("New array is less than myarray:");

        foreach(string j in myarray)
        {
            Console.WriteLine(j);
        }

    }
}
```

**Output:**

```cs
Original Array:
C#
Java
C++
Python
HTML
CSS
JavaScript
Length of myarray: 7

New array is less than myarray:
C#
Java
C++
Python

```

**例 2:**

```cs
// C# program to resize the 
// elements of the 1-D array
using System;

public class GFG {

    // Main method
    static public void Main()
    {

        // create and initialize array
        string[] myarray = {"C#", "C++", "Ruby", 
                         "Java", "PHP", "Perl"};

        // Display original string before Resize
        Console.WriteLine("Original Array:");

        foreach(string i in myarray)
        {
            Console.WriteLine(i);
        }

        // Length of old array
        int len = myarray.Length;
        Console.WriteLine("Length of myarray: "+len);
        Console.WriteLine();

        // Resize the element of myarray 
        // and create a new array
        // Here new array is greater than
        // original array so, all the element 
        // from myarray is copied to new array
        // and remaining will be null
        Array.Resize(ref myarray, 10);

        Console.WriteLine("New array is greater than myarray:");

        foreach(string j in myarray)
        {
            Console.WriteLine(j);
        }

        // Length of new array
        int len1 = myarray.Length;
        Console.WriteLine("Length of New Array: "+len1);

    }
}
```

**Output:**

```cs
Original Array:
C#
C++
Ruby
Java
PHP
Perl
Length of myarray: 6

New array is greater than myarray:
C#
C++
Ruby
Java
PHP
Perl

Length of New Array: 10

```

**参考:**[https://docs . Microsoft . com/en-us/dotnet/API/system . array . resize？view=netcore-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.array.resize?view=netcore-2.1)