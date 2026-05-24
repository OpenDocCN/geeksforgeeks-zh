# C# |排序集与集合的交集

> 原文:[https://www . geeksforgeeks . org/c-sharp-sorted set-with-a-collection/](https://www.geeksforgeeks.org/c-sharp-intersection-of-sortedset-with-a-collection/)

**SortedSet** 类表示按排序顺序排列的对象集合。这个班隶属于*T3 系统。集合.通用*命名空间。**排序集< T >。intersecwith(IEnumerable<T>)**方法用于修改当前 SortedSet < T >对象，使其只包含也在指定集合中的元素。

**属性:**

*   在 C# 中，SortedSet 类可用于存储、移除或查看元素。
*   它保持升序，不存储重复的元素。
*   如果必须存储唯一元素并保持升序，建议使用 SortedSet 类。

**语法:**

```cs
mySortedSet1.IntersectWith(mySortedSet2);

```

这里 *mySortedSet1* 和 *mySortedSet2* 是两个 SortedSet 的对象。

**异常:**如果排序集为*空*，该方法将给出*参数空异常*。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to get the Intersection of 2 SortedSets
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedSet of integers
        SortedSet<int> mySortedSet1 = new SortedSet<int>();

        // adding elements in mySortedSet1
        mySortedSet1.Add(2);
        mySortedSet1.Add(4);
        mySortedSet1.Add(6);
        mySortedSet1.Add(8);
        mySortedSet1.Add(10);

        // Creating a SortedSet of integers
        SortedSet<int> mySortedSet2 = new SortedSet<int>();

        // adding elements in mySortedSet
        mySortedSet2.Add(4);
        mySortedSet2.Add(5);
        mySortedSet2.Add(7);
        mySortedSet2.Add(8);
        mySortedSet2.Add(9);

        Console.WriteLine("The intersection of mySortedSet1 and mySortedSet2:");

        mySortedSet1.IntersectWith(mySortedSet2);

        // To display the intersection 
        // of mySortedSet1 and mySortedSet2
        foreach(int i in mySortedSet1)
        {
            Console.WriteLine(i);
        }
    }
}
```

**Output:**

```cs
The intersection of mySortedSet1 and mySortedSet2: 
4
8

```

**例 2:**

```cs
// C# code to get the Intersection of 2 SortedSets
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedSet of strings
        SortedSet<string> mySortedSet1 = new SortedSet<string>();

        // adding elements in mySortedSet1
        mySortedSet1.Add("Geeks");
        mySortedSet1.Add("for");
        mySortedSet1.Add("Geeks");
        mySortedSet1.Add("Noida");
        mySortedSet1.Add("Data Structures");

        // Creating a SortedSet of strings
        SortedSet<string> mySortedSet2 = new SortedSet<string>();

        // adding elements in mySortedSet
        mySortedSet2.Add("Geeks");
        mySortedSet2.Add("Java");
        mySortedSet2.Add("Geeks Classes");
        mySortedSet2.Add("C++");
        mySortedSet2.Add("Noida");

        Console.WriteLine("The Intersection of mySortedSet1 and mySortedSet2:");

        mySortedSet1.IntersectWith(mySortedSet2);

        // To display the intersection of
        // mySortedSet1 and mySortedSet2
        foreach(string str in mySortedSet1)
        {
            Console.WriteLine(str);
        }
    }
}
```

**Output:**

```cs
The Intersection of mySortedSet1 and mySortedSet2 is: 
Geeks
Noida

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . sorted set-1 . intersecwit？view=netcore-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedset-1.intersectwith?view=netcore-2.1)