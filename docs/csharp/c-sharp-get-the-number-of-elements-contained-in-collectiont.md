# C# |获取集合<t>中包含的元素个数</t>

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-in-collection 中包含的元素数量/](https://www.geeksforgeeks.org/c-sharp-get-the-number-of-elements-contained-in-collectiont/)

**收藏<T1**T>。Count 属性用于获取集合< **T** >中实际包含的元素数量。

**语法:**

```cs
public int Count { get; }

```

**返回值:**集合中实际包含的元素数量<**>。**

**下面给出了一些例子，以便更好地理解实现:**

****例 1:****

```cs
// C# code to get the number of
// elements contained in the Collection
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
    }
}
```

****输出:****

```cs
Count : 5
A
B
C
D
E 
```

****例 2:****

```cs
// C# code to get the number of
// elements contained in the Collection
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
    }
}
```

****输出:****

```cs
Count : 4
2
3
4
5 
```

****注意:**检索该属性的值是一个 O(1)运算。**

****参考:****

*   **[https://docs . Microsoft . com/en-us/dotnet/API/system . collections . object model . collection-1 . count？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.objectmodel.collection-1.count?view=netframework-4.7.2)**