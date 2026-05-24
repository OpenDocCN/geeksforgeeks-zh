# C# |从集合中移除所有元素

> 原文:[https://www . geesforgeks . org/c-sharp-从集合中移除所有元素/](https://www.geeksforgeeks.org/c-sharp-remove-all-elements-from-the-collectiont/)

**收藏<T1**T>。清除方法用于清除集合< **T** >中的所有元素。

**语法:**

```cs
public void Clear ();

```

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to remove all
// elements from the Collection
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

        // To print the count of elements in Collection
        Console.WriteLine("Count : " + myColl.Count);

        // Displaying the elements in myColl
        foreach(string str in myColl)
        {
            Console.WriteLine(str);
        }

        // Removing all the elements from Collection
        myColl.Clear();

        // To print the count of elements in Collection
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
Count : 0

```

**例 2:**

```cs
// C# code to remove all
// elements from the Collection
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
        myColl.Add(5);

        // To print the count of elements in Collection
        Console.WriteLine("Count : " + myColl.Count);

        // Displaying the elements in myColl
        foreach(int i in myColl)
        {
            Console.WriteLine(i);
        }

        // Removing all the elements from Collection
        myColl.Clear();

        // To print the count of elements in Collection
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
Count : 4
2
3
4
5
Count : 0

```

**注:**

*   Count 被设置为零，并且集合元素对其他对象的引用也被释放。
*   这个方法是一个 O(n)运算，其中 n 是 Count。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . object model . collection-1 . clear？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.objectmodel.collection-1.clear?view=netframework-4.7.2)