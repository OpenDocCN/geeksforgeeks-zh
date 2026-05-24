# C# |统计列表中的元素总数

> 原文:[https://www . geeksforgeeks . org/c-sharp-计算列表中元素的总数/](https://www.geeksforgeeks.org/c-sharp-count-the-total-number-of-elements-in-the-list/)

**列表**类表示可通过索引访问的对象列表。它属于*体系。集合.泛型*命名空间。List 类可以用来创建不同类型的集合，如整数、字符串等。列表类还提供了搜索、排序和操作列表的方法。**名单。计数属性**用于获取列表中包含的元素总数。

**属性:**

*   它不同于数组。一个**列表可以动态调整大小**但是数组不能。
*   列表类可以接受 null 作为引用类型的有效值，并且它还**允许重复元素**。
*   如果计数等于容量，则通过重新分配内部阵列，列表的容量会自动增加。在添加新元素之前，现有元素将被复制到新数组中。

**语法:**

```cs
list_name.Count
```

下面的程序说明了计数属性的使用:

**例 1:**

```cs
// C# code to get the number of
// elements contained in List
using System;
using System.Collections.Generic;

class Geeks {

    // Main Method
    public static void Main()
    {

        // Creating a List of integers
        List<int> firstlist = new List<int>();

        // adding elements in firstlist
        for (int i = 4; i < 10; i++) {
            firstlist.Add(i * 2);
        }

        // To get the number of
        // elements in the List
        Console.WriteLine(firstlist.Count);
    }
}
```

**输出:**

```cs
6

```

**例 2:**

```cs
// C# code to get the number of
// elements contained in List
using System;
using System.Collections.Generic;

class Geeks {

    // Main Method
    public static void Main()
    {

        // Creating a List of integers
        List<int> firstlist = new List<int>();

        // To get the number of
        // elements in the List
        Console.WriteLine(firstlist.Count);
    }
}
```

**输出:**

```cs
0

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . list-1 . count？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.count?view=netframework-4.7.2)