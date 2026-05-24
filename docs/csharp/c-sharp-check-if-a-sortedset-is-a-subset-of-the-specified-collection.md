# C# |检查排序集是否是指定集合的子集

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-a-sorted set-是指定集合的子集/](https://www.geeksforgeeks.org/c-sharp-check-if-a-sortedset-is-a-subset-of-the-specified-collection/)

**SortedSet** 类表示按排序顺序排列的对象集合。这个班隶属于*T3 系统。集合.通用*命名空间。**排序集< T >。issubestof(IEnumerable<T>)方法**用于检查一个 SortedSet < T >对象是否是指定集合的子集。

**属性:**

*   在 C# 中，SortedSet 类可用于存储、移除或查看元素。
*   它保持升序，不存储重复的元素。
*   如果必须存储唯一元素并保持升序，建议使用 SortedSet 类。

**语法:**

```cs
mySet1.IsSubsetOf(mySet2);

```

在这里，*我自己 1* 和*我自己 2* 是排序集。

**返回值:**如果 SortedSet < **T** >对象是其他的子集，则此方法返回 *True* ，否则返回 *false* 。

**异常:**如果*排序集*为空，该方法返回*参数空异常*。

**例 1:**

```cs
// C# code to Check if a SortedSet is a
// subset of the specified collection
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedSet of integers
        SortedSet<int> mySet1 = new SortedSet<int>();

        // Inserting elements in SortedSet
        mySet1.Add(2);
        mySet1.Add(3);
        mySet1.Add(4);
        mySet1.Add(5);

        // Creating a SortedSet of integers
        SortedSet<int> mySet2 = new SortedSet<int>();

        // Inserting elements in SortedSet
        mySet2.Add(3);
        mySet2.Add(4);
        mySet2.Add(5);
        mySet2.Add(6);

        // Check if a SortedSet is a subset
        // of the specified collection
        // It should return false as SortedSet mySet2
        // is not a subset of SortedSet mySet1
        Console.WriteLine(mySet2.IsSubsetOf(mySet1));
    }
}
```

**Output:**

```cs
False

```

**例 2:**

```cs
// C# code to Check if a SortedSet is a
// subset of the specified collection
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedSet of strings
        SortedSet<string> mySet1 = new SortedSet<string>();

        // Inserting elements in SortedSet
        mySet1.Add("A");
        mySet1.Add("B");
        mySet1.Add("C");
        mySet1.Add("D");
        mySet1.Add("A");

        // Creating a SortedSet of strings
        SortedSet<string> mySet2 = new SortedSet<string>();

        // Inserting elements in SortedSet
        mySet2.Add("B");
        mySet2.Add("C");
        mySet2.Add("D");
        mySet2.Add("D");

        // Check if a SortedSet is a subset
        // of the specified collection
        // It should return true as SortedSet mySet2
        // is subset of SortedSet mySet1
        Console.WriteLine(mySet2.IsSubsetOf(mySet1));
    }
}
```

**Output:**

```cs
True

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . sorted set-1 . issubestof？view=netcore-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedset-1.issubsetof?view=netcore-2.1)