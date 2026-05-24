# C# |从哈希集中移除所有元素

> 原文:[https://www . geeksforgeeks . org/c-sharp-remove-all-elements-from-a-hashset/](https://www.geeksforgeeks.org/c-sharp-remove-all-elements-from-a-hashset/)

一个 **HashSet** 是一个独特元素的无序集合。它属于*T3 系统。集合.通用*命名空间。它用于我们希望防止在集合中插入重复项的情况。就性能而言，与列表相比更好。 **HashSet <t>。清除方法</t>** 用于从 HashSet 对象中移除所有元素。

**语法:**

```cs
mySet.Clear(); 

```

这里， *mySet* 是 HashSet 的名字。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to remove all elements from HashSet
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HashSet of integers
        HashSet<int> mySet = new HashSet<int>();

        // Inserting even numbers less than
        // equal to 20 in HashSet mySet1
        for (int i = 0; i < 10; i++) {
            mySet.Add(i * 2);
        }

        // Displaying the number of elements in HashSet
        Console.WriteLine(mySet.Count);

        // Removing all the elements from HashSet
        mySet.Clear();

        // Displaying the number of elements in HashSet
        // after removing all the elements from it
        Console.WriteLine(mySet.Count);
    }
}
```

**Output:**

```cs
10
0

```

**例 2:**

```cs
// C# code to remove all elements from HashSet
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HashSet of strings
        HashSet<string> mySet = new HashSet<string>();

        // Inserting elements in HashSet
        mySet.Add("Geeks");
        mySet.Add("and");
        mySet.Add("GeeksforGeeks");
        mySet.Add("are");
        mySet.Add("the");
        mySet.Add("best");

        // Displaying the number of elements in HashSet
        Console.WriteLine(mySet.Count);

        // Removing all the elements from HashSet
        mySet.Clear();

        // Displaying the number of elements in HashSet
        // after removing all the elements from it
        Console.WriteLine(mySet.Count);

        // Inserting elements in HashSet
        mySet.Add("Join");
        mySet.Add("Geeks");
        mySet.Add("Classes");

        // Displaying the number of elements in HashSet
        Console.WriteLine(mySet.Count);
    }
}
```

**Output:**

```cs
6
0
3

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . hashset-1 . clear？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.hashset-1.clear?view=netframework-4.7.2)