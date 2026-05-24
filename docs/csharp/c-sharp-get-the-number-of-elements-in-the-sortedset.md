# C# |获取排序集中的元素个数

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-the-number-in-sorted set/](https://www.geeksforgeeks.org/c-sharp-get-the-number-of-elements-in-the-sortedset/)

**SortedSet** 类表示按排序顺序排列的对象集合。这个班隶属于*T3 系统。集合.通用*命名空间。**排序集< T >。计数属性**用于获取排序集中的元素数量。

**属性:**

*   在 C# 中，SortedSet 类可用于存储、移除或查看元素。
*   它保持升序，不存储重复的元素。
*   如果必须存储唯一元素并保持升序，建议使用 SortedSet 类。

**语法:**

```cs
mySortedSet.Count

```

这里， *mySortedSet* 是一个 SortedSet。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to get the number of
// elements in the SortedSet
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedSet of integers
        SortedSet<int> mySortedSet = new SortedSet<int>();

        // adding elements in mySortedSet
        mySortedSet.Add(1);
        mySortedSet.Add(2);
        mySortedSet.Add(3);
        mySortedSet.Add(4);
        mySortedSet.Add(5);

        // Displaying the number of elements in
        // the SortedSet using "Count" function
        Console.WriteLine("The number of elements in mySortedSet are: " 
                                                  + mySortedSet.Count);
    }
}
```

**Output:**

```cs
The number of elements in mySortedSet are: 5

```

**例 2:**

```cs
// C# code to get the number of
// elements in the SortedSet
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedSet of strings
        SortedSet<string> mySortedSet = new SortedSet<string>();

        // adding elements in mySortedSet
        mySortedSet.Add("Hey");
        mySortedSet.Add("GeeksforGeeks");
        mySortedSet.Add("and");
        mySortedSet.Add("Geeks Classes");

        // Displaying the number of elements in
        // the SortedSet using "Count" function
        Console.WriteLine("The number of elements in mySortedSet are: " 
                                                   + mySortedSet.Count);
    }
}
```

**Output:**

```cs
The number of elements in mySortedSet are: 4

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . sorted set-1 . count？view=netcore-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedset-1.count?view=netcore-2.1)