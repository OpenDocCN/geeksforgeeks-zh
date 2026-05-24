# C# |排序列表的容量

> 原文:[https://www . geeksforgeeks . org/c-sharp-a-sorted list 的容量/](https://www.geeksforgeeks.org/c-sharp-capacity-of-a-sortedlist/)

**排序列表。容量属性**用于获取或设置排序列表对象的容量。

**语法:**

```cs
public virtual int Capacity { get; set; }

```

**返回值:**该属性返回**系统类型的元素个数。排序列表对象可以包含的 Int32** 。

**异常:**

*   **ArgumentOutOfRangeException:**如果赋值小于 SortedList 对象中当前的元素数。
*   **OutOfMemoryException:** 如果系统上没有足够的可用内存。

**容量与计数:**

*   计数总是小于容量。添加元素时，如果计数超过容量，则容量将通过在复制旧元素和添加新元素之前重新分配内部数组来自动增加。
*   容量是列表在根据需要调整大小之前可以存储的元素数量。但是计数是列表中实际存在的元素的数量。
*   如果容量比计数大得多，用户可以通过调用 TrimExcess 方法或将容量显式设置为较低的值来减少容量。
*   如果容量已明确确定，则内部数组也将重新分配以容纳指定的容量，并且所有元素都将被复制。
*   检索容量属性的值是一个 0(1)操作，而设置容量是一个 0(n)操作，其中 n 是新容量。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# program to illustrate the
// Capacity Property of SortedList
using System;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a SortedList of integers
        // Here we are not setting
        // Capacity explicitly
        SortedList mySortedList = new SortedList();

        // Adding elements to SortedList
        mySortedList.Add("1", "C#");
        mySortedList.Add("2", "Java");
        mySortedList.Add("3", "DSA");
        mySortedList.Add("4", "Python");
        mySortedList.Add("5", "C");

        // Printing the Capacity of mySortedList
        Console.WriteLine("Capacity Is: " + mySortedList.Capacity);

        // Printing the Count of mySortedList
        Console.WriteLine("Count Is: " + mySortedList.Count);

        // Adding some more
        // elements in mySortedList
        mySortedList.Add("6", "C++");
        mySortedList.Add("7", "HTML");
        mySortedList.Add("8", "CSS");
        mySortedList.Add("9", "Web");
        mySortedList.Add("10", "DBMS");
        mySortedList.Add("11", "CN");
        mySortedList.Add("12", "Ruby");
        mySortedList.Add("13", "Perl");
        mySortedList.Add("14", "R");
        mySortedList.Add("15", "GO");
        mySortedList.Add("16", "Scala");
        mySortedList.Add("17", "Big Data");

        // Printing the Capacity of mySortedList
        // It will give output 32 as internally
        // SortedList is resized
        Console.WriteLine("Capacity Is: " + mySortedList.Capacity);

        // Printing the Count of mySortedList
        Console.WriteLine("Count Is: " + mySortedList.Count);
    }
}
```

**输出:**

```cs
Capacity Is: 16
Count Is: 5
Capacity Is: 32
Count Is: 17

```

**例 2:**

```cs
// C# program to illustrate the
// Capacity Property of SortedList
using System;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a SortedList of integers
        // Here we are setting Capacity
        // explicitly i.e. 7
        SortedList mySortedList = new SortedList(7);

        // Printing the Capacity of mySortedList
        Console.WriteLine("Capacity Is: " + mySortedList.Capacity);

        // Printing the Count of mySortedList
        Console.WriteLine("Count Is: " + mySortedList.Count);

        // Adding elements to SortedList
        mySortedList.Add("1", "C#");
        mySortedList.Add("2", "Java");
        mySortedList.Add("3", "DSA");
        mySortedList.Add("4", "Python");
        mySortedList.Add("5", "C");

        // Printing the Capacity of mySortedList
        Console.WriteLine("Capacity Is: " + mySortedList.Capacity);

        // Printing the Count of mySortedList
        Console.WriteLine("Count Is: " + mySortedList.Count);

        // Adding some more
        // elements in firstlist
        mySortedList.Add("6", "C++");
        mySortedList.Add("7", "HTML");
        mySortedList.Add("8", "CSS");
        mySortedList.Add("9", "Web");

        // Printing the Capacity of mySortedList
        // It will give output 14 as internally
        // SortedList is resized
        Console.WriteLine("Capacity Is: " + mySortedList.Capacity);

        // Printing the Count of firstlist
        Console.WriteLine("Count Is: " + mySortedList.Count);
    }
}
```

**输出:**

```cs
Capacity Is: 7
Count Is: 0
Capacity Is: 7
Count Is: 5
Capacity Is: 14
Count Is: 9

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . sorted list . capacity？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.sortedlist.capacity?view=netframework-4.7.2)