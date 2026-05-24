# C# |向列表中添加元素

> 原文:[https://www . geesforgeks . org/c-sharp-向列表中添加元素/](https://www.geeksforgeeks.org/c-sharp-adding-an-element-to-the-list/)

**列表。添加(T)方法**用于在列表末尾添加一个对象。

**列表属性:**

*   它不同于数组。一个**列表可以动态调整大小**但是数组不能。
*   列表类可以接受 null 作为引用类型的有效值，并且它**也允许重复元素**。
*   如果计数等于容量，则通过重新分配内部阵列，列表的容量会自动增加。在添加新元素之前，现有元素将被复制到新数组中。
*   如果计数小于容量，则此方法为 0(1)运算。如果需要增加容量来容纳新元素，那么这个方法就变成了 O(n)操作。

**语法:**

```cs
public void Add (T item);
```

**参数:**

> **项:**要添加到*系统类型列表末尾的指定对象。对象*。

以下程序说明了如何在列表中添加元素:

**例 1:**

```cs
// C# program to add element in List<T>
using System;
using System.Collections.Generic;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a List of integers
        List<int> firstlist = new List<int>();

        // adding elements in firstlist
        for (int i = 4; i < 10; i++) {
            firstlist.Add(i * 2);
        }

        // Displaying elements of firstlist
        // by using foreach loop
        foreach(int element in firstlist)
        {
            Console.WriteLine(element);
        }
    }
}
```

**输出:**

```cs
8
10
12
14
16
18

```

**例 2:**

```cs
// C# program to add element in List<T>
using System;
using System.Collections.Generic;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a List of integers
        List<int> firstlist = new List<int>();

        // adding elements in firstlist
        firstlist.Add(1);
        firstlist.Add(2);
        firstlist.Add(3);
        firstlist.Add(4);

        // Adding some duplicate
        // elements in firstlist
        firstlist.Add(3);
        firstlist.Add(4);

        // Displaying elements of firstlist
        // by using foreach loop
        foreach(int element in firstlist)
        {
            Console.WriteLine(element);
        }
    }
}
```

**输出:**

```cs
1
2
3
4
3
4

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . list-1 . add？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.add?view=netframework-4.7.2)