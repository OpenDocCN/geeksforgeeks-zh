# C# |检查 SortedSet 和指定的集合是否共享公共元素

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-sorted set-and-a-specified-collection-share-common-elements/](https://www.geeksforgeeks.org/c-sharp-check-if-sortedset-and-a-specified-collection-share-common-elements/)

**SortedSet** 类表示按排序顺序排列的对象集合。这个班隶属于*T3 系统。集合.通用*命名空间。**排序集合<t>。重叠(IEnumerable <t>)方法</t></t>** 用于检查排序集和指定集合是否共享公共元素。

**属性:**

*   在 C# 中，SortedSet 类可用于存储、移除或查看元素。
*   它保持升序，不存储重复的元素。
*   如果必须存储唯一元素并保持升序，建议使用 SortedSet 类。

**语法:**

```cs
mySortedSet1.Overlaps(mySortedSet2);

```

这里*我的 ortedSet1* 和*我的 ortedSet2* 是两个排序集。

**返回值:**如果 *mySortedSet1* 和 *mySortedSet2* 共享至少一个公共元素**，则函数返回 ***True*** ，否则返回 ***False*** 。**

**异常:**如果排序集为*空*，该方法将给出 ArgumentNullException。

**例 1:**

```cs
// C# code to Check if SortedSet
// and a specified collection
// share common elements
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedSet of integers
        SortedSet<int> mySortedSet1 = new SortedSet<int>();

        // adding elements in mySortedSet1
        mySortedSet1.Add(5);
        mySortedSet1.Add(6);
        mySortedSet1.Add(7);
        mySortedSet1.Add(8);
        mySortedSet1.Add(9);

        // Creating a SortedSet of integers
        SortedSet<int> mySortedSet2 = new SortedSet<int>();

        // adding elements in mySortedSet2
        mySortedSet2.Add(7);
        mySortedSet2.Add(8);
        mySortedSet2.Add(9);
        mySortedSet2.Add(10);
        mySortedSet2.Add(11);

        // Check if SortedSet and a specified
        // collection share common elements
        Console.WriteLine(mySortedSet1.Overlaps(mySortedSet2));
    }
}
```

**Output:**

```cs
True

```

**例 2:**

```cs
// C# code to Check if SortedSet
// and a specified collection
// share common elements
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedSet of strings
        SortedSet<string> mySortedSet1 = new SortedSet<string>();

        // adding elements in mySortedSet1
        mySortedSet1.Add("A");
        mySortedSet1.Add("B");
        mySortedSet1.Add("C");
        mySortedSet1.Add("D");
        mySortedSet1.Add("E");

        // Creating a SortedSet of strings
        SortedSet<string> mySortedSet2 = new SortedSet<string>();

        // adding elements in mySortedSet2
        mySortedSet2.Add("F");
        mySortedSet2.Add("G");
        mySortedSet2.Add("H");
        mySortedSet2.Add("I");
        mySortedSet2.Add("J");

        // Check if SortedSet and a specified
        // collection share common elements
        Console.WriteLine(mySortedSet1.Overlaps(mySortedSet2));
    }
}
```

**Output:**

```cs
False

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . sorted set-1 .重叠？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedset-1.overlaps?view=netframework-4.7.2)