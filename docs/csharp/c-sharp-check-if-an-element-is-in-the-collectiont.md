# C# |检查集合中是否有元素

> 原文:[https://www . geeksforgeeks . org/c-sharp-check-如果元素在集合中/](https://www.geeksforgeeks.org/c-sharp-check-if-an-element-is-in-the-collectiont/)

**收藏<T1**T>。Contains(T) 方法用于确定一个元素是否在集合< **T** >中。

**语法:**

```cs
public bool Contains (T item);

```

这里 ***项*** 是集合< **T** >中要定位的对象。对于引用类型，该值可以为 null。

**返回值:**如果在收藏中找到物品<**>此方法返回 ***真*** ，否则返回 ***假*** 。**

**下面给出了一些例子，以便更好地理解实现:**

****例 1:****

```cs
// C# code to check if an
// element is in the Collection
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

        // Checking if an element is in the Collection
        // The function returns "True" if the
        // item is present in Collection
        // else returns "False"
        Console.WriteLine(myColl.Contains("A"));
    }
}
```

****输出:****

```cs
True 
```

****例 2:****

```cs
// C# code to check if an
// element is in the Collection
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

        // Checking if an element is in the Collection
        // The function returns "True" if the
        // item is present in Collection
        // else returns "False"
        Console.WriteLine(myColl.Contains(6));
    }
}
```

****输出:****

```cs
False 
```

****注意:**该方法执行**线性搜索**。因此，这个方法是一个 O(n)运算，其中 n 是 Count。**

****参考:****

*   **[https://docs . Microsoft . com/en-us/dotnet/API/system . collections . object model . collection-1 . contains？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.objectmodel.collection-1.contains?view=netframework-4.7.2)**