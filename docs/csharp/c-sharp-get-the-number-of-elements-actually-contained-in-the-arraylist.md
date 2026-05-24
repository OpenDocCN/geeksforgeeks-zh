# C# |获取数组列表中实际包含的元素个数

> 原文:[https://www . geesforgeks . org/c-sharp-获取数组列表中实际包含的元素数量/](https://www.geeksforgeeks.org/c-sharp-get-the-number-of-elements-actually-contained-in-the-arraylist/)

**数组列表**表示可以单独索引的对象的有序集合。它基本上是数组的替代。它还允许动态内存分配、添加、搜索和排序列表中的项目。**数组列表。Count** 属性获取数组列表中实际包含的元素数量。

**数组列表类的属性:**

*   可以随时在数组列表集合中添加或删除元素。
*   数组列表不能保证排序。
*   数组列表的容量是数组列表可以容纳的元素数量。
*   可以使用整数索引访问此集合中的元素。此集合中的索引从零开始。
*   它还允许重复元素。
*   不支持在数组列表集合中使用多维数组作为元素。

**语法:**

```cs
public virtual int Count { get; }

```

**返回值:**数组列表中实际包含的元素个数。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to get the number of elements
// actually contained in the ArrayList
using System;
using System.Collections;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an ArrayList
        ArrayList myList = new ArrayList();

        // Displaying the number of elements in ArrayList
        Console.WriteLine("Number of elements : " + myList.Count);

        // Adding elements to ArrayList
        myList.Add(1);
        myList.Add(2);
        myList.Add(3);
        myList.Add(4);
        myList.Add(5);

        // Displaying the number of elements in ArrayList
        Console.WriteLine("Number of elements : " + myList.Count);
    }
}
```

**Output:**

```cs
Number of elements : 0
Number of elements : 5

```

**例 2:**

```cs
// C# code to get the number of elements
// actually contained in the ArrayList
using System;
using System.Collections;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an ArrayList
        ArrayList myList = new ArrayList();

        // Displaying the number of elements in ArrayList
        Console.WriteLine("Number of elements : " + myList.Count);

        // Adding elements to ArrayList
        myList.Add("First");
        myList.Add("Second");
        myList.Add("Third");
        myList.Add("Fourth");
        myList.Add("Fifth");
        myList.Add("Sixth");
        myList.Add("Seventh");
        myList.Add("Eighth");

        // Displaying the number of elements in ArrayList
        Console.WriteLine("Number of elements : " + myList.Count);
    }
}
```

**Output:**

```cs
Number of elements : 0
Number of elements : 8

```

**注:**

*   容量是数组列表可以存储的元素数量。计数是数组列表中实际存在的元素数量。
*   容量始终大于或等于计数。如果添加元素时计数超过容量，则在复制旧元素和添加新元素之前，通过重新分配内部数组来自动增加容量。
*   检索该属性的值是一个 O(1)操作。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . ArrayList . count？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.count?view=netframework-4.7.2)