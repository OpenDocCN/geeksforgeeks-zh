# C# |检查排序列表对象是否有固定大小

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-a-sorted list-object-has-fixed-size/](https://www.geeksforgeeks.org/c-sharp-check-if-a-sortedlist-object-has-a-fixed-size/)

SortedList 类是按键排序的**(键，值)对**的集合。这些对可以通过键和以及索引(从零开始的索引)来访问。这属于**体系。集合**命名空间。**排序列表。IsFixedSize** 属性用于检查 SortedList 对象是否有固定大小。

**排序列表的属性:**

*   Internally, the sorted list object maintains two arrays. The first array is used to store the elements in the list, that is, keys, and the second array is used to store related values.
*   The keyword cannot be blank, but the value can be blank.
*   SortedList is slower than Hashtable because it uses sorting.
*   The capacity of sorting list can be dynamically increased by redistribution.
*   Keys in the sorted list cannot be duplicated, but values can be duplicated.
*   Sorting lists can be sorted by keywords using IComparer (ascending or descending order).

**语法:**

```cs
public virtual bool IsFixedSize { get; }

```

**返回值:**如果 SortedList 对象的大小固定，则该属性返回 ***True*** ，否则返回 ***False*** 。该属性的默认值为 ***假*** 。

**例:**

```cs
// C# code to check if a SortedList
// object has a fixed size
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

        // Checking if a SortedList
        // object has a fixed size
        Console.WriteLine(mySortedList.IsFixedSize);
    }
}
```

**输出:**

```cs
False

```

**注意:**

*   The read-only collection is not allowed to add, remove or modify elements after it is created.
*   Retrieving the value of this attribute is an O(1) operation.