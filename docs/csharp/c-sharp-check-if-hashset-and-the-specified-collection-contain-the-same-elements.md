# C# |检查 HashSet 和指定的集合是否包含相同的元素

> 原文:[https://www . geeksforgeeks . org/c-sharp-check-if-hashset-and-the-specified-collection-contain-the-the-same-elements/](https://www.geeksforgeeks.org/c-sharp-check-if-hashset-and-the-specified-collection-contain-the-same-elements/)

一个 **HashSet** 是一个无序的**独特元素**的集合。它属于*T5 系统。集合.通用* 命名空间。它用于我们希望防止在集合中插入重复项的情况。就性能而言，与列表相比更好。 **HashSet <t>。SetEquals(IEnumerable <t>)方法</t></t>** 用于检查一个 HashSet 和指定的集合是否包含相同的元素。

**语法:**

```cs
mySet1.SetEquals(mySet2);

```

在这里，*我自己 1* 和*我自己 2* 是 HashSets 对象。

**返回类型:**此方法返回 *True* 如果 my STAT1 等于 my stat2，则返回 *False* 。

**异常:**如果哈希表为*空*，该方法将给出*参数异常*。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to check if HashSet and the specified
// collection contain the same elements.
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
        mySet2.Add("Geeks");
        mySet2.Add("GeeksforGeeks");
        mySet2.Add("GeeksClasses");
        mySet2.Add("GeeksQuiz");

        // Check if both HashSets contains same elements
        Console.WriteLine(mySet1.SetEquals(mySet2));
    }
}
```

**Output:**

```cs
True

```

**例 2:**

```cs
// C# code to check if HashSet and the specified
// collection contain the same elements.
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
        mySet2.Add(5);
        mySet2.Add(10);
        mySet2.Add(15);
        mySet2.Add(20);

        // Check if both HashSets contains same elements
        Console.WriteLine(mySet1.SetEquals(mySet2));
    }
}
```

**Output:**

```cs
False

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . hashset-1 . setequals？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.hashset-1.setequals?view=netframework-4.7.2)