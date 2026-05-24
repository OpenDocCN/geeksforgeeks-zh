# C# |检查排序集是否是指定集合的超集

> 原文:[https://www . geeksforgeeks . org/c-sharp-check-if-a-sorted set-is-superset-of-specific-collection/](https://www.geeksforgeeks.org/c-sharp-check-if-a-sortedset-is-a-superset-of-the-specified-collection/)

**SortedSet** 类表示按排序顺序排列的对象集合。这个班属于*系统。集合.通用*命名空间。**排序集合< T >。issuesperstof(IEnumerable<T>)**方法用于检查一个 SortedSet < T >对象是否是指定集合的超集。

**属性:**

*   在 C# 中，SortedSet 类可用于存储、移除或查看元素。
*   它保持升序，不存储重复的元素。
*   如果必须存储唯一元素并保持升序，建议使用 SortedSet 类。

**语法:**

```cs
mySet1.IsSupersetOf(mySet2);

```

这里*本人 1* 和*本人 2* 是排序集的两个对象。

**返回值:**如果 SortedSet < **T** >对象是其他对象的超集，则该方法返回 *True* ，否则返回 *false* 。

**异常:**如果排序集为空，该方法将给出*参数空异常*。

以下是说明使用**排序集< T >的程序。方法:**

**例 1 :**

```cs
// C# code to Check if a SortedSet is a
// superset of the specified collection
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedSet of strings
        SortedSet<string> mySet1 = new SortedSet<string>();

        // Inserting elements in SortedSet
        mySet1.Add("Geeks");
        mySet1.Add("GeeksQuiz");

        // Creating a SortedSet of strings
        SortedSet<string> mySet2 = new SortedSet<string>();

        // Inserting elements in SortedSet
        mySet2.Add("DS");
        mySet2.Add("C++");
        mySet2.Add("Java");
        mySet2.Add("JavaScript");
        mySet2.Add("GeeksQuiz");
        mySet2.Add("Geeks");

        // Check if a SortedSet is a superset
        // of the specified collection
        // It should return true as SortedSet mySet2
        // is superset of SortedSet mySet1
        Console.WriteLine(mySet2.IsSupersetOf(mySet1));
    }
}
```

**Output:**

```cs
True

```

**例 2:**

```cs
// C# code to Check if a SortedSet is a
// superset of the specified collection
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

        // Check if a SortedSet is a superset
        // of the specified collection
        // It should return false as SortedSet mySet2
        // is not a superset of SortedSet mySet1
        Console.WriteLine(mySet2.IsSupersetOf(mySet1));
    }
}
```

**Output:**

```cs
False

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . sorted set-1 . issuesperstof？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedset-1.issupersetof?view=netframework-4.7.2)