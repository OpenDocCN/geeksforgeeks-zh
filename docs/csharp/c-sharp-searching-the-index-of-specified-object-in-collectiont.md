# C# |在集合<t>中搜索指定对象的索引</t>

> 原文:[https://www . geeksforgeeks . org/c-sharp-搜索指定对象在集合中的索引/](https://www.geeksforgeeks.org/c-sharp-searching-the-index-of-specified-object-in-collectiont/)

**收藏<T1**T>。IndexOf(T) 方法用于搜索指定的对象，并返回整个集合中第一个出现的从零开始的索引< **T** >。

**语法:**

```cs
public int IndexOf (T item);

```

这里 ***项*** 是列表< **T** >中要定位的对象。参考类型的值可以是 *null* 。

**返回值:**此方法返回整个集合中第一个出现的项目的从零开始的索引<**>，如果找到，否则为-1。**

**下面给出了一些例子，以便更好地理解实现:**

****例 1:****

```cs
// C# code to search for the specified
// object and returns the zero-based
// index of the first occurrence within
// the entire Collection
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
        myColl.Add("D");
        myColl.Add("E");

        // Displaying the elements in myColl
        foreach(string str in myColl)
        {
            Console.WriteLine(str);
        }

        // Searching for the specified object
        // and returns the zero-based index of
        // the first occurrence within the entire
        // Collection. If the object doesn't contain the
        // object, then -1 is returned
        Console.WriteLine("Index : " + myColl.IndexOf("D"));
    }
}
```

****输出:****

```cs
A
B
C
D
D
E
Index : 3 
```

****例 2:****

```cs
// C# code to search for the specified
// object and returns the zero-based
// index of the first occurrence within
// the entire Collection
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

        // Displaying the elements in myColl
        foreach(int i in myColl)
        {
            Console.WriteLine(i);
        }

        // Searching for the specified object
        // and returns the zero-based index of
        // the first occurrence within the entire
        // Collection. If the object doesn't contain the
        // object, then -1 is returned
        Console.WriteLine("Index : " + myColl.IndexOf(7));
    }
}
```

****输出:****

```cs
2
3
4
5
Index : -1 
```

****注:****

*   **集合< **T** >从第一个元素开始向前搜索，到最后一个元素结束。**
*   **此方法使用默认的相等比较器[相等比较器< **T** >来确定相等。默认](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.equalitycomparer-1.default?view=netframework-4.7.2)为 **T** ，列表中的数值类型。**
*   **此方法执行线性搜索。因此，这个方法是一个 **O(n)** 运算，其中 n 是 Count。**

****参考:****

*   **[https://docs . Microsoft . com/en-us/dotnet/API/system . collections . object model . collection-1 . indexof？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.objectmodel.collection-1.indexof?view=netframework-4.7.2)**