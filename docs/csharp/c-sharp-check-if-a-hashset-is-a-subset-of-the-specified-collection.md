# C# |检查哈希集是否是指定集合的子集

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-a-hashset-is-subset-the-specific-collection/](https://www.geeksforgeeks.org/c-sharp-check-if-a-hashset-is-a-subset-of-the-specified-collection/)

一个 **HashSet** 是一个无序的**独特元素**的集合。在*T5 系统中找到。集合.通用* 命名空间。它用于我们希望防止在集合中插入重复项的情况。就性能而言，与列表相比更好。 **HashSet <t>。issubestof(IEnumerable<t>)方法</t></t>** 用于检查一个 *HashSet* 对象是否是指定集合的子集。

**语法:**

```cs
mySet1.IsSubsetOf(mySet2);

```

这里*我自己 1* 和*我自己 2* 是 HashSets。

**返回类型:**如果 HashSet <t>对象是另一个子集的子集，则该方法返回 *true* ，否则返回 *false* 。</t>

**异常:**如果 HashSet 为 *null* ，该方法将给出 ArgumentNullException。

下面给出的是一些例子，以更好地理解实现:

**例子 1:**

```cs
// C# code to Check if a HashSet is
// a subset of the specified collection
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HashSet of integers
        HashSet<int> mySet1 = new HashSet<int>();

        // Inserting elements in HashSet
        // mySet1 only contains even numbers less than
        // equal to 10
        for (int i = 1; i <= 5; i++)
            mySet1.Add(2 * i);

        // Creating a HashSet of integers
        HashSet<int> mySet2 = new HashSet<int>();

        // Inserting elements in HashSet
        // mySet2 contains all numbers from 1 to 10
        for (int i = 1; i <= 10; i++)
            mySet2.Add(i);

        // Check if a HashSet mySet1 is a subset
        // of the HashSet mySet2
        Console.WriteLine(mySet1.IsSubsetOf(mySet2));
    }
}
```

**输出:**

```cs
True

```

**例 2:**

```cs
// C# code to Check if a HashSet is
// a subset of the specified collection
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HashSet of integers
        HashSet<int> mySet1 = new HashSet<int>();

        // Creating a HashSet of integers
        HashSet<int> mySet2 = new HashSet<int>();

        // Inserting elements in HashSet mySet2.
        // mySet2 contains all numbers from 1 to 10
        for (int i = 1; i <= 10; i++)
            mySet2.Add(i);

        // Check if a HashSet mySet1 is a subset
        // of the HashSet mySet2
        // It should return true, as an empty HashSet is
        // subset of other HashSet
        Console.WriteLine(mySet1.IsSubsetOf(mySet2));
    }
}
```

**Output:**

```cs
True

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . hashset-1 . issubestof？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.hashset-1.issubsetof?view=netframework-4.7.2)