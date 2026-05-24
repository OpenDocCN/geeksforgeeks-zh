# C# |检查哈希集是否是指定集合的适当子集

> 原文:[https://www . geeksforgeeks . org/c-sharp-check-if-a-hashset-is-a-specified-subset-the-specified-collection/](https://www.geeksforgeeks.org/c-sharp-check-if-a-hashset-is-a-proper-subset-of-the-specified-collection/)

一个 **HashSet** 是一个无序的**独特元素**的集合。它属于*T5 系统。集合.通用* 命名空间。它用于我们希望防止在集合中插入重复项的情况。就性能而言，与列表相比更好。 **HashSet < T >。ispropertsubtof(IEnumerable<T>)**方法用于检查一个 *HashSet < T >* 对象是否是指定集合的适当子集。

**语法:**

```cs
mySet1.IsProperSubsetOf(mySet2);

```

这里，我自己 1 和我自己 2 是两个*hashsset*。

**返回值:**如果*本人 1* 是*本人 2* 的适当子集，则该方法返回*真*，否则返回*假*。

**异常:**如果哈希表为*空*，此方法将给出*参数空异常*。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to Check if a HashSet is a proper
// subset of the specified collection
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HashSet of strings
        HashSet<string> mySet1 = new HashSet<string>();

        // Inserting elements in HashSet
        mySet1.Add("Geeks");
        mySet1.Add("GeeksQuiz");

        // Creating a HashSet of strings
        HashSet<string> mySet2 = new HashSet<string>();

        // Inserting elements in HashSet
        mySet2.Add("DS");
        mySet2.Add("C++");
        mySet2.Add("Java");
        mySet2.Add("JavaScript");
        mySet2.Add("GeeksQuiz");
        mySet2.Add("Geeks");

        // Check if a HashSet is a proper
        // subset of the specified collection
        Console.WriteLine(mySet1.IsProperSubsetOf(mySet2));
    }
}
```

**Output:**

```cs
True

```

**例 2:**

```cs
// C# code to Check if a HashSet is a proper
// subset of the specified collection
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HashSet of integers
        HashSet<int> mySet1 = new HashSet<int>();

        // Inserting elements in HashSet
        mySet1.Add(4);
        mySet1.Add(8);
        mySet1.Add(12);
        mySet1.Add(16);

        // Creating a HashSet of integers
        HashSet<int> mySet2 = new HashSet<int>();

        // Inserting elements in HashSet
        mySet2.Add(4);
        mySet2.Add(8);
        mySet2.Add(15);
        mySet2.Add(20);

        // Check if a HashSet is a proper
        // subset of the specified collection
        Console.WriteLine(mySet1.IsProperSubsetOf(mySet2));
    }
}
```

**Output:**

```cs
False

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . hashset-1 . ispropertsubstof？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.hashset-1.ispropersubsetof?view=netframework-4.7.2)