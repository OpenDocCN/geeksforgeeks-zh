# C# |从集合中移除对象的第一个匹配项

> 原文:[https://www . geeksforgeeks . org/c-sharp-从集合中移除第一个出现的对象/](https://www.geeksforgeeks.org/c-sharp-removing-first-occurrence-of-object-from-collectiont/)

**收藏<T1**T>。移除(T) 用于从集合< **T** >中移除特定对象的第一次出现。

**语法:**

```cs
public bool Remove (T item);

```

在这里， ***项*** 是从集合< **T** >中移除的对象。对于引用类型，该值可以为 null。

**返回值:** **真**如果物品移除成功，否则，**假**。如果在原始集合< **T** >中没有找到项目，该方法也返回 **False** 。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to remove the first
// occurrence of a specific object
// from the Collection
using System;
using System.Collections.Generic;
using System.Collections.ObjectModel;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a collection of strings
        Collection<string> myColl = new Collection<string>();

        // Adding elements in Collection myColl
        myColl.Add("A");
        myColl.Add("B");
        myColl.Add("C");
        myColl.Add("D");
        myColl.Add("E");

        // Displaying the number of elements in myColl
        Console.WriteLine("Count : " + myColl.Count);

        // Displaying the elements in myColl
        foreach(string str in myColl)
        {
            Console.WriteLine(str);
        }

        // Removing the first occurrence of
        // a specific object from the Collection
        myColl.Remove("C");

        // Displaying the number of elements in myColl
        Console.WriteLine("Count : " + myColl.Count);

        // Displaying the elements in myColl
        foreach(string str in myColl)
        {
            Console.WriteLine(str);
        }
    }
}
```

**输出:**

```cs
Count : 5
A
B
C
D
E
Count : 4
A
B
D
E

```

**例 2:**

```cs
// C# code to remove the first
// occurrence of a specific object
// from the Collection
using System;
using System.Collections.Generic;
using System.Collections.ObjectModel;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a collection of ints
        Collection<int> myColl = new Collection<int>();

        // Adding elements in Collection myColl
        myColl.Add(2);
        myColl.Add(3);
        myColl.Add(4);
        myColl.Add(4);
        myColl.Add(5);

        // Displaying the number of elements in myColl
        Console.WriteLine("Count : " + myColl.Count);

        // Displaying the elements in myColl
        foreach(int i in myColl)
        {
            Console.WriteLine(i);
        }

        // Removing the first occurrence of
        // a specific object from the Collection
        myColl.Remove(4);

        // Displaying the number of elements in myColl
        Console.WriteLine("Count : " + myColl.Count);

        // Displaying the elements in myColl
        foreach(int i in myColl)
        {
            Console.WriteLine(i);
        }
    }
}
```

**输出:**

```cs
Count : 5
2
3
4
4
5
Count : 4
2
3
4
5

```

**注意:**此方法执行线性搜索。因此这个方法是一个 **O(n)** 运算，其中 n 是 Count。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . object model . collection-1 . remove？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.objectmodel.collection-1.remove?view=netframework-4.7.2)