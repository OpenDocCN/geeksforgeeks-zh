# C# |从排序集中删除所有元素

> 原文:[https://www . geeksforgeeks . org/c-sharp-remove-all-elements-from-sorted set/](https://www.geeksforgeeks.org/c-sharp-remove-all-elements-from-the-sortedset/)

**SortedSet** 类表示按排序顺序排列的对象集合。这个班隶属于*T3 系统。集合.通用*命名空间。**排序集< T >。清除方法**用于从排序集中移除所有元素。

**属性:**

*   在 C# 中，SortedSet 类可用于存储、移除或查看元素。
*   它保持升序，不存储重复的元素。
*   如果必须存储唯一元素并保持升序，建议使用 SortedSet 类。

**语法:**

```cs
mySortedSet.Clear();

```

这里， *mySortedSet* 是 SortedSet 的名字。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to remove all the elements
// from SortedSet
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedSet of strings
        SortedSet<string> mySortedSet = new SortedSet<string>();

        // adding elements in mySortedSet
        mySortedSet.Add("A");
        mySortedSet.Add("B");
        mySortedSet.Add("C");
        mySortedSet.Add("D");
        mySortedSet.Add("E");

        // Displaying number of elements in mySortedSet
        // before Removing all the elements
        Console.WriteLine("Number of elements in mySortedSet are : " 
                                               + mySortedSet.Count);

        // Displaying the element in mySortedSet
        foreach(string str in mySortedSet)
        {
            Console.WriteLine(str);
        }

        // Removing all the elements from mySortedSet
        mySortedSet.Clear();

        // Displaying number of elements in mySortedSet
        // after Removing all the elements
        Console.WriteLine("Number of elements in mySortedSet are : " 
                                               + mySortedSet.Count);
    }
}
```

**Output:**

```cs
Number of elements in mySortedSet are : 5
A
B
C
D
E
Number of elements in mySortedSet are : 0

```

**例 2:**

```cs
// C# code to remove all the elements
// from SortedSet
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedSet of integers
        SortedSet<int> mySortedSet = new SortedSet<int>();

        // adding elements in mySortedSet
        for (int i = 1; i <= 6; i++) {
            mySortedSet.Add(2 * i + 1);
        }

        // Displaying number of elements in mySortedSet
        // before Removing all the elements
        Console.WriteLine("Number of elements in mySortedSet are : " 
                                               + mySortedSet.Count);

        // Displaying the element in mySortedSet
        foreach(int i in mySortedSet)
        {
            Console.WriteLine(i);
        }

        // Removing all the elements from mySortedSet
        mySortedSet.Clear();

        // Displaying number of elements in mySortedSet
        // after Removing all the elements
        Console.WriteLine("Number of elements in mySortedSet are : "
                                               + mySortedSet.Count);
    }
}
```

**Output:**

```cs
Number of elements in mySortedSet are : 6
3
5
7
9
11
13
Number of elements in mySortedSet are : 0

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . sorted set-1 . clear？view=netcore-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedset-1.clear?view=netcore-2.1)