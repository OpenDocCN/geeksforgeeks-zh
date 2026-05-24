# C# |获取 SortedList 中包含的元素个数

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-in-sorted list/](https://www.geeksforgeeks.org/c-sharp-get-the-number-of-elements-contained-in-sortedlist/)

**排序列表。计数属性**用于获取排序列表对象中包含的元素数量。

**语法:**

```cs
public virtual int Count { get; }
```

**属性值:**sorted list 对象中包含的元素数量。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# Program to count the number
// of elements in SortedList
using System;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating object of SortedList
        // fslist is the SortedList object
        SortedList fslist = new SortedList();

        // Count property is used to get the
        // number of key/value pairs in fslist
        // It will give 0 as no pairs are present
        Console.WriteLine(fslist.Count);
    }
}
```

**Output:**

```cs
0

```

**例 2:**

```cs
// C# Program to count the number
// of elements in SortedList
using System;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating object of SortedList
        // fslist is the SortedList object
        SortedList fslist = new SortedList();

        // Count property is used to get the
        // number of key/value pairs in fslist
        // It will give 0 as no pairs are present
        Console.WriteLine(fslist.Count);

        // Adding key/value pairs in fslist
        fslist.Add("1", "GFG");
        fslist.Add("2", "Geeks");
        fslist.Add("3", "for");
        fslist.Add("4", "Geeks");

        // Count property is used to get the
        // number of key/value pairs in fslist
        // It will give output 4
        Console.WriteLine(fslist.Count);
    }
}
```

**Output:**

```cs
0
4

```

**注:**

*   键/值对可以作为 DictionaryEntry 对象访问。
*   计数是实际存在于排序列表中的元素数量，但 [*容量*](https://www.geeksforgeeks.org/c-capacity-of-a-sortedlist/) 是排序列表对象可以存储的元素数量。
*   [*容量*](https://www.geeksforgeeks.org/c-capacity-of-a-sortedlist/) 始终大于等于 Count。如果添加元素时计数超过容量，则在复制旧元素和添加新元素之前，通过重新分配内部数组来自动增加容量。
*   检索该属性的值是一个 O(1)操作。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . sorted list . count？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.sortedlist.count?view=netframework-4.7.2)