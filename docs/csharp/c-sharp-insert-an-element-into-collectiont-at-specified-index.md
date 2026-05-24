# C# |将元素插入集合<t>中指定的索引</t>

> 原文:[https://www . geeksforgeeks . org/c-sharp-insert-element-in-collection-at-specific-index/](https://www.geeksforgeeks.org/c-sharp-insert-an-element-into-collectiont-at-specified-index/)

**收藏<T1**T>。Insert(Int32，T) 方法用于将元素插入集合< **T** >中的指定索引处。

**语法:**

```cs
public void Insert (int index, T item);

```

**参数:**

> **索引:**应该插入项目的从零开始的索引。
> **项:**插入的对象。对于引用类型，该值可以为 null。

**异常:**如果*指数*小于零 ***或*** 指数大于计数，此方法将给出**argumentout of range 异常**。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to insert an element into
// the Collection at the specified index
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

        // Inserting an element into the
        // Collection at the specified index
        myColl.Insert(2, "GFG");

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
Count : 6
A
B
GFG
C
D
E

```

**例 2:**

```cs
// C# code to insert an element into
// the Collection at the specified index
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

        // Displaying the number of elements in myColl
        Console.WriteLine("Count : " + myColl.Count);

        // Displaying the elements in myColl
        foreach(int i in myColl)
        {
            Console.WriteLine(i);
        }

        // Inserting an element into the
        // Collection at the specified index
        // This should raise "ArgumentOutOfRangeException"
        // as index is less than 0
        myColl.Insert(-1, 8);

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

**运行时错误:**

> 未处理异常:
> 系统。ArgumentOutOfRangeException:索引必须在列表的范围内。
> 参数名称:索引

**注:**

*   集合< **T** >接受 null 作为引用类型的有效值，并允许重复元素。
*   如果索引等于计数，则项目被添加到集合< **T** >的末尾。
*   这个方法是一个 O(n)运算，其中 n 是 Count。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . object model . collection-1 . insert？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.objectmodel.collection-1.insert?view=netframework-4.7.2)