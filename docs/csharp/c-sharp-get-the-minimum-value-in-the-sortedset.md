# C# |获取排序集中的最小值

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-the-mini-value-in-sorted set/](https://www.geeksforgeeks.org/c-sharp-get-the-minimum-value-in-the-sortedset/)

**SortedSet** 类表示按排序顺序排列的对象集合。这个班隶属于*T3 系统。集合.通用*命名空间。**排序集< T >。最小属性**用于获取排序集< T >中的最小值，由比较器定义。

**属性:**

*   在 C# 中，SortedSet 类可用于存储、移除或查看元素。
*   它保持升序，不存储重复的元素。
*   如果必须存储唯一元素并保持升序，建议使用 SortedSet 类。

**语法:**

```cs
mySet.Min

```

这里，*我自己*是 SortedSet 的对象。

**返回值:**排序集中的最小值。

以下程序说明了**排序集< T >的使用。最小属性**:

**例 1:**

```cs
// C# code to get the minimum value
// in the SortedSet
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedSet of integers
        SortedSet<int> mySet = new SortedSet<int>();

        // Inserting elements into SortedSet
        for (int i = 0; i < 10; i++) {
            mySet.Add(i);
        }

        // Displaying the minimum value in the SortedSet
        Console.WriteLine("The minimum element in SortedSet is : " + mySet.Min);
    }
}
```

**Output:**

```cs
The minimum element in SortedSet is : 0

```

**例 2:**

```cs
// C# code to get the minimum value
// in the SortedSet
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedSet of strings
        SortedSet<string> mySet = new SortedSet<string>();

        // Inserting elements into SortedSet
        mySet.Add("A");
        mySet.Add("B");
        mySet.Add("C");
        mySet.Add("D");
        mySet.Add("E");
        mySet.Add("F");

        // Displaying the minimum value in the SortedSet
        Console.WriteLine("The minimum element in SortedSet is : " + mySet.Min);
    }
}
```

**Output:**

```cs
The minimum element in SortedSet is : A

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . sorted set-1 . min？view=netcore-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedset-1.min?view=netcore-2.1)