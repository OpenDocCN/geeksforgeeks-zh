# C# |在集合<t>末尾添加一个对象</t>

> 原文:[https://www . geeksforgeeks . org/c-sharp-添加一个对象到集合末尾/](https://www.geeksforgeeks.org/c-sharp-add-an-object-to-the-end-of-collectiont/)

**收藏<T1**T>。Add(T) 方法用于将一个对象添加到集合的末尾< **T** >。

**语法:**

```cs
public void Add (T item);

```

这里 ***项*** 是要添加到集合< **T** >末尾的对象。对于引用类型，该值可以为 null。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to add an object to
// the end of the Collection
using System;
using System.Collections.Generic;
using System.Collections.ObjectModel;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a collection of strings
        Collection<string> myColl = new Collection<string>();

        myColl.Add("A");
        myColl.Add("B");
        myColl.Add("C");
        myColl.Add("D");
        myColl.Add("E");

        // Displaying the number of elements in Collection
        Console.WriteLine("The number of elements in myColl are : " 
                                                   + myColl.Count);

        // Displaying the elements in Collection
        Console.WriteLine("The elements in myColl are : ");

        foreach(string str in myColl)
        {
            Console.WriteLine(str);
        }
    }
}
```

**输出:**

```cs
The number of elements in myColl are : 5
The elements in myColl are : 
A
B
C
D
E

```

**例 2:**

```cs
// C# code to add an object to
// the end of the Collection
using System;
using System.Collections.Generic;
using System.Collections.ObjectModel;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a collection of ints
        Collection<int> myColl = new Collection<int>();

        myColl.Add(2);
        myColl.Add(3);
        myColl.Add(4);
        myColl.Add(5);

        // Displaying the number of elements in Collection
        Console.WriteLine("The number of elements in myColl are : "
                                                   + myColl.Count);

        // Displaying the elements in Collection
        Console.WriteLine("The elements in myColl are : ");

        foreach(int i in myColl)
        {
            Console.WriteLine(i);
        }
    }
}
```

**输出:**

```cs
The number of elements in myColl are : 4
The elements in myColl are : 
2
3
4
5

```

**注:**

*   集合< **T** >接受 null 作为引用类型的有效值，并允许重复元素。
*   这个方法是一个 **O(1)** 运算。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . object model . collection-1 . add？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.objectmodel.collection-1.add?view=netframework-4.7.2)