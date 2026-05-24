# C# |从排序集中删除指定项目

> 原文:[https://www . geesforgeks . org/c-sharp-remove-a-item-from-sorted set/](https://www.geeksforgeeks.org/c-sharp-remove-a-specified-item-from-sortedset/)

**SortedSet** 类表示按排序顺序排列的对象集合。这个班隶属于*T3 系统。集合.通用*命名空间。**排序集< T >。移除(T)方法**用于从排序集中移除指定的项目。

**属性:**

*   在 C# 中，SortedSet 类可用于存储、移除或查看元素。
*   它保持升序，不存储重复的元素。
*   如果必须存储唯一元素并保持升序，建议使用 SortedSet 类。

**语法:**

```cs
public bool Remove (T item);

```

这里，**项**是要从排序集中删除的指定项。

**注意:**如果 SortedSet < **T** >对象不包含指定元素，则对象保持不变，不会抛出异常。

**例 1:**

```cs
// C# code to remove a specified element
// from the SortedSet
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

        // Removing element "4" if found
        mySortedSet.Remove(4);

        // Displaying the elements in mySortedSet
        foreach(int i in mySortedSet)
        {
            Console.WriteLine(i);
        }

        Console.WriteLine("After Using Method");

        // Removing element "14" if found
        mySortedSet.Remove(14);

        // Displaying the element in mySortedSet
        foreach(int i in mySortedSet)
        {
            Console.WriteLine(i);
        }
    }
}
```

**Output:**

```cs
2
6
8
10
After Using Method
2
6
8
10

```

**例 2:**

```cs
// C# code to remove the specified
// element from SortedSet
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

        // Removing element "C" if found
        mySortedSet.Remove("C");

        // Displaying the element in mySortedSet
        foreach(string str in mySortedSet)
        {
            Console.WriteLine(str);
        }
    }
}
```

**Output:**

```cs
A
B
D
E

```