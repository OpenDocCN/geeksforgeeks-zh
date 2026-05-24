# C# |检查排序列表对象是否同步

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-a-sorted list-object-is-synchronized/](https://www.geeksforgeeks.org/c-sharp-check-if-a-sortedlist-object-is-synchronized/)

SortedList 类是按键排序的**(键，值)对**的集合。这些对可以通过键和以及索引(从零开始的索引)来访问。这属于**T3 系统。收藏**命名空间。**排序列表。IsSynchronized 属性**用于获取一个值，该值指示对 SortedList 对象的访问是否同步(线程安全)。

**属性:**

*   SortedList 元素可以通过它的键或索引来访问。
*   SortedList 对象在内部维护两个数组来存储列表元素，即一个数组用于键，另一个数组用于关联值。
*   键不能为空，但值可以为空。
*   排序列表对象的**容量**是排序列表可以容纳的元素数量。
*   排序列表不允许重复键。
*   由于排序，对 SortedList 对象的操作往往比对 Hashtable 对象的操作慢。
*   可以使用整数索引访问此集合中的元素。此集合中的索引从零开始。

**语法:**

```cs
public virtual bool IsSynchronized { get; }

```

**返回值:**如果对 SortedList 对象的访问是同步的(线程安全的)，则此方法返回 ***True*** ，否则此方法返回 ***False*** 。默认值为 ***假*** 。

以下程序说明了**排序列表的使用。同步属性:**

**例 1:**

```cs
// C# code to check if a SortedList
// object is synchronized (thread safe)
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an SortedList
        SortedList mySortedList = new SortedList();

        // Checking if a SortedList object
        // is synchronized (thread safe) or not
        Console.WriteLine(mySortedList.IsSynchronized);
    }
}
```

**Output:**

```cs
False

```

**例 2:**

```cs
// C# code to check if a SortedList
// object is synchronized (thread safe)
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an SortedList
        SortedList mySortedList = new SortedList();

        // Adding elements to SortedList
        mySortedList.Add("1", "one");
        mySortedList.Add("2", "two");
        mySortedList.Add("3", "three");
        mySortedList.Add("4", "four");
        mySortedList.Add("5", "five");

        // Creating a synchronized wrapper
        // around the SortedList.
        SortedList mySortedList_1 = SortedList.Synchronized(mySortedList);

        // Checking if a SortedList object
        // is synchronized (thread safe) or not
        Console.WriteLine(mySortedList_1.IsSynchronized);
    }
}
```

**Output:**

```cs
True

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . sorted list . is synchronized？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.sortedlist.issynchronized?view=netframework-4.7.2)