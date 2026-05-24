# C# |检查散列集合是否包含指定的元素

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-a-hashset-contains-specific-element/](https://www.geeksforgeeks.org/c-sharp-check-if-a-hashset-contains-the-specified-element/)

一个 **HashSet** 是**独特元素**的无序集合。在 ***系统中找到。Collections.Generic*** 命名空间。它用于我们希望防止在集合中插入重复项的情况。就性能而言，与列表相比更好。 **HashSet <t>。Contains(T)方法</t>** 用于检查一个 HashSet <t>对象是否包含指定的元素。</t>

**语法:**

```cs
mySet.Contains(T item);

```

这里， *mySet* 是 HashSet 的名称，*项*是 HashSet <t>对象中需要定位的元素。</t>

**返回类型:**如果 *HashSet* 对象包含指定元素，则该方法返回*true*；否则，*为假*。

下面给出的是一些例子来更好地理解实现:

**例子 1:**

```cs
// C# code to check if a HashSet
// contains the specified element
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HashSet of strings
        HashSet<string> mySet = new HashSet<string>();

        // Inserting elements in HashSet
        mySet.Add("DS");
        mySet.Add("C++");
        mySet.Add("Java");
        mySet.Add("JavaScript");

        // Check if a HashSet contains
        // the specified element
        if (mySet.Contains("Java"))
            Console.WriteLine("Required Element is present");
        else
            Console.WriteLine("Required Element is not present");
    }
}
```

**输出:**

```cs
Required Element is present

```

**例 2:**

```cs
// C# code to check if a HashSet
// contains the specified element
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

        // Check if a HashSet contains
        // the specified element
        if (mySet.Contains(5))
            Console.WriteLine("Required Element is present");
        else
            Console.WriteLine("Required Element is not present");
    }
}
```

**Output:**

```cs
Required Element is not present

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . hashset-1 . contains？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.hashset-1.contains?view=netframework-4.7.2)