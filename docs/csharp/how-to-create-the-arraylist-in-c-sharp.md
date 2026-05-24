# 如何在 C# 中创建数组列表

> 原文:[https://www . geeksforgeeks . org/如何创建 c-sharp 中的数组列表/](https://www.geeksforgeeks.org/how-to-create-the-arraylist-in-c-sharp/)

**ArrayList()构造函数**用于初始化 ArrayList 类的一个新实例，该实例将为空，并具有默认的初始容量。[数组列表](https://www.geeksforgeeks.org/arraylist-in-c-sharp/)表示可以单独索引的对象的有序集合。它基本上是数组的替代。它还允许动态内存分配、添加、搜索和排序列表中的项目。

**语法:**

```cs
public ArrayList ();
```

**要点:**

*   The number of elements that an array can hold is called the [capacity](https://www.geeksforgeeks.org/c-sharp-get-or-set-the-number-of-elements-that-the-arraylist-can-contain/) of the array list. If the element is to be added to the array list, the capacity will be automatically increased by reallocating the internal array.
*   If the size of the collection can be estimated, specifying the initial capacity will eliminate the need to perform a large number of resizing operations when adding elements to the array list.
*   This constructor is an O(1) operation.

**例 1:**

```cs
// C# Program to illustrate how
// to create a ArrayList
using System;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // arrlist is the ArrayList object
        // ArrayList() is the constructor
        // used to initializes a new
        // instance of the ArrayList class
        ArrayList arrlist = new ArrayList();

        // Count property is used to get the
        // number of elements in ArrayList
        // It will give 0 as no elements
        // are present currently
        Console.WriteLine(arrlist.Count);
    }
}
```

**输出:**

```cs
0

```