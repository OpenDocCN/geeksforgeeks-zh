# c# | HashSet 中的元素个数

> 原文:[https://www . geesforgeks . org/c-sharp-元素数量-in-hashset/](https://www.geeksforgeeks.org/c-sharp-number-of-elements-in-hashset/)

一个 **HashSet** 是一个无序的**独特元素**的集合。在*系统中找到。集合.通用*命名空间。它用于我们希望防止在集合中插入重复项的情况。就性能而言，与列表相比更好。可以使用 **HashSet <t>。计数属性</t>** 计算哈希表中的元素数量。

**语法:**

```cs
mySet.Count;

```

这里*我自己*是 HashSet

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to get the number of
// elements that are contained in HashSet
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HashSet of integers
        HashSet<int> mySet = new HashSet<int>();

        // Inserting elements in HashSet
        for (int i = 0; i < 5; i++) {
            mySet.Add(i * 2);
        }

        // To get the number of
        // elements that are contained in HashSet
        Console.WriteLine(mySet.Count);
    }
}
```

**Output:**

```cs
5

```

**例 2:**

```cs
// C# code to get the number of
// elements that are contained in HashSet
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HashSet of integers
        HashSet<int> mySet = new HashSet<int>();

        // To get the number of
        // elements that are contained in HashSet.
        // Note that, here the HashSet is empty
        Console.WriteLine(mySet.Count);
    }
}
```

**Output:**

```cs
0

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . hashset-1 . count？view = net framework-4 . 7 . 2 # System _ Collections _ Generic _ HashSet _ 1 _ Count](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.hashset-1.count?view=netframework-4.7.2# System_Collections_Generic_HashSet_1_Count)