# C# |检查哈希集和指定集合是否共享公共元素

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-a-hashset-and-a-specified-collection-share-common-elements/](https://www.geeksforgeeks.org/c-sharp-check-if-a-hashset-and-a-specified-collection-share-common-elements/)

一个 **HashSet** 是一个无序的**独特元素**的集合。在*T5 系统中找到。集合.通用* 命名空间。它用于我们希望防止在集合中插入重复项的情况。就性能而言，与列表相比更好。 *HashSet <t>。重叠(IEnumerable <t>)方法</t></t>* 用于检查当前 *HashSet* 对象和指定集合是否共享公共元素。

**语法:**

```cs
mySet1.Overlaps(mySet2);

```

*其中，mySet1 和 mySet2 为 HashSets。*

**返回类型:**如果两个哈希集至少共享一个公共元素，则该方法返回 *true* ，否则返回 *false* 。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to Check if a HashSet and a
// specified collection share common elements
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
        mySet1.Add("GeeksforGeeks");
        mySet1.Add("GeeksClasses");
        mySet1.Add("GeeksQuiz");

        // Creating a HashSet of strings
        HashSet<string> mySet2 = new HashSet<string>();

        // Inserting elements in HashSet
        mySet2.Add("DS");
        mySet2.Add("C++");
        mySet2.Add("Java");
        mySet2.Add("JavaScript");

        // Check if a HashSet and a specified
        // collection share common elements
        Console.WriteLine(mySet1.Overlaps(mySet2));
    }
}
```

**Output:**

```cs
False

```

**例 2:**

```cs
// C# code to Check if a HashSet and a
// specified collection share common elements
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

        // Check if a HashSet and a specified
        // collection share common elements
        Console.WriteLine(mySet1.Overlaps(mySet2));
    }
}
```

**Output:**

```cs
True

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . hashset-1 .重叠？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.hashset-1.overlaps?view=netframework-4.7.2)