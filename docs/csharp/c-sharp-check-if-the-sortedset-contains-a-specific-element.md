# C# |检查排序集是否包含特定元素

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-the-sorted set-contains-specific-element/](https://www.geeksforgeeks.org/c-sharp-check-if-the-sortedset-contains-a-specific-element/)

**SortedSet** 类表示按排序顺序排列的对象集合。这个班隶属于*T3 系统。集合.通用*命名空间。**排序集< T >。Contains(T)方法**用于检查排序集是否包含特定元素。

**属性:**

*   在 C# 中，SortedSet 类可用于存储、移除或查看元素。
*   它保持升序，不存储重复的元素。
*   如果必须存储唯一元素并保持升序，建议使用 SortedSet 类。

**语法:**

```cs
public virtual bool Contains (T item);

```

这里 **T** 是类型参数，即集合中元素的类型。

**返回值:**如果集合包含指定项目，则返回**真**，否则返回**假**。

**例 1:**

```cs
// C# code to check if the SortedSet
// contains a specific element
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedSet of integers
        SortedSet<int> mySortedSet = new SortedSet<int>();

        // adding elements in mySortedSet
        mySortedSet.Add(2);
        mySortedSet.Add(4);
        mySortedSet.Add(6);
        mySortedSet.Add(8);
        mySortedSet.Add(10);

        // Checking if the SortedSet contains
        // a specific element
        Console.WriteLine(mySortedSet.Contains(6));
    }
}
```

**Output:**

```cs
True

```

**例 2:**

```cs
// C# code to check if the SortedSet
// contains a specific element
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedSet of strings
        SortedSet<string> mySortedSet = new SortedSet<string>();

        // adding elements in mySortedSet
        mySortedSet.Add("Mumbai");
        mySortedSet.Add("Bangalore");
        mySortedSet.Add("Chandigarh");
        mySortedSet.Add("Noida");
        mySortedSet.Add("Jaipur");
        mySortedSet.Add("Kolkata");

        // Checking if the SortedSet contains
        // a specific element
        Console.WriteLine(mySortedSet.Contains("Delhi"));
    }
}
```

**Output:**

```cs
False

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . sorted set-1 . contains？view=netcore-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedset-1.contains?view=netcore-2.1)