# C# |列表容量

> 原文:[https://www.geeksforgeeks.org/c-sharp-capacity-of-a-list/](https://www.geeksforgeeks.org/c-sharp-capacity-of-a-list/)

**列表< T >。容量属性**用于获取或设置内部数据结构在不调整大小的情况下可以容纳的元素总数。

**列表属性:**

*   它不同于数组。列表可以动态调整大小，但数组不能。
*   列表类可以接受 null 作为引用类型的有效值，并且它还允许重复的元素。
*   如果计数等于容量，则列表的容量会通过重新分配内部数组而自动增加。在添加新元素之前，现有元素将被复制到新数组中。

**容量 Vs[T2](https://www.geeksforgeeks.org/c-count-the-total-number-of-elements-in-the-list/)**计数 :

*   计数总是小于容量。添加元素时，如果计数超过容量，则容量将通过在复制旧元素和添加新元素之前重新分配内部数组来自动增加。
*   容量是列表在根据需要调整大小之前可以存储的元素数量。但是计数是列表中实际存在的元素的数量。
*   如果容量比计数大得多，用户可以通过调用 TrimExcess 方法或将容量显式设置为较低的值来减少容量。
*   如果容量已明确确定，则内部数组也将重新分配以容纳指定的容量，并且所有元素都将被复制。
*   检索容量属性的值是一个 0(1)操作，而设置容量是一个 0(n)操作，其中 n 是新容量。

**语法:**

```cs
public int Capacity { get; set; }

```

**返回值:**该方法返回列表< T >在类型*系统需要调整大小之前可以包含的元素数量。Int32* 。

**异常:**

*   **argumentoutofrangerexception:**如果容量设置为小于**的值，则[计数为](https://www.geeksforgeeks.org/c-count-the-total-number-of-elements-in-the-list/)T5。**
*   **OutOfMemoryException :** 如果系统上没有足够的可用内存。

以下程序说明了容量属性的使用:

**例 1:**

```cs
// C# program to illustrate the
// Capacity Property of List<T>
using System;
using System.Collections.Generic;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a List of integers
        // Here we are not setting
        // Capacity explicitly
        List<int> firstlist = new List<int>();

        // adding elements in firstlist
        firstlist.Add(1);
        firstlist.Add(2);
        firstlist.Add(3);
        firstlist.Add(4);

        // Printing the Capacity of firstlist
        Console.WriteLine("Capacity Is: " + firstlist.Capacity);

        // Printing the Count of firstlist
        Console.WriteLine("Count Is: " + firstlist.Count);

        // Adding some more
        // elements in firstlist
        firstlist.Add(5);
        firstlist.Add(6);

        // Printing the Capacity of firstlist
        // It will give output 8 as internally
        // List is resized
        Console.WriteLine("Capacity Is: " + firstlist.Capacity);

        // Printing the Count of firstlist
        Console.WriteLine("Count Is: " + firstlist.Count);
    }
}
```

**输出:**

```cs
Capacity Is: 4
Count Is: 4
Capacity Is: 8
Count Is: 6

```

**例 2:**

```cs
// C# program to illustrate the
// Capacity Property of List<T>
using System;
using System.Collections.Generic;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a List of integers
        // Here we are setting Capacity
        // explicitly i.e.
        List<int> firstlist = new List<int>(10);

        // Printing the Capacity of firstlist
        Console.WriteLine("Capacity Is: " + firstlist.Capacity);

        // Printing the Count of firstlist
        Console.WriteLine("Count Is: " + firstlist.Count);

        // adding elements in firstlist
        firstlist.Add(1);
        firstlist.Add(2);
        firstlist.Add(3);
        firstlist.Add(4);

        // Printing the Capacity of firstlist
        Console.WriteLine("Capacity Is: " + firstlist.Capacity);

        // Printing the Count of firstlist
        Console.WriteLine("Count Is: " + firstlist.Count);

        // Adding some more
        // elements in firstlist
        firstlist.Add(5);
        firstlist.Add(6);

        // Printing the Capacity of firstlist
        // It will give output 10 as we have
        // already set the Capacity
        Console.WriteLine("Capacity Is: " + firstlist.Capacity);

        // Printing the Count of firstlist
        Console.WriteLine("Count Is: " + firstlist.Count);
    }
}
```

**输出:**

```cs
Capacity Is: 10
Count Is: 0
Capacity Is: 10
Count Is: 4
Capacity Is: 10
Count Is: 6

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . list-1 . capacity？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.capacity?view=netframework-4.7.2)