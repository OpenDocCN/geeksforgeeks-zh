# C# |从列表中删除一系列元素

> 原文:[https://www . geeksforgeeks . org/c-sharp-从列表中删除一系列元素/](https://www.geeksforgeeks.org/c-sharp-removing-a-range-of-elements-from-the-list/)

**列表< T >。移除范围(Int32，Int32)方法**用于从列表< T >中移除一系列元素。

**列表属性:**

*   它不同于数组。列表可以动态调整大小，但数组不能。
*   列表类可以接受 null 作为引用类型的有效值，并且它还允许重复的元素。
*   如果 **[计数](https://www.geeksforgeeks.org/c-count-the-total-number-of-elements-in-the-list/)** 变为等于 **[容量](https://www.geeksforgeeks.org/c-capacity-of-a-list/)** ，则列表的容量通过重新分配内部数组而自动增加。在添加新元素之前，现有元素将被复制到新数组中。

**语法:**

```cs
public void RemoveRange (int index, int count);
```

**参数:**

> **索引:**是要删除的元素范围的从零开始的索引。
> 
> **计数:**是要删除的元素的数量。

**异常:**

*   **argumentoutofrangerexception:**如果指数小于零或**T3】计数 T5】小于零。**
*   **参数异常:**如果索引和 **[计数](https://www.geeksforgeeks.org/c-count-the-total-number-of-elements-in-the-list/)** 不表示列表中元素的有效范围< T >。

以下程序说明了**列表< T >的使用。移除范围(Int32，Int32)方法:**

**例 1:**

```cs
// C# Program to remove a range of
// elements from the List
using System;
using System.Collections;
using System.Collections.Generic;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating an List<T> of strings
        List<String> firstlist = new List<String>();

        // Adding elements to List
        firstlist.Add("Geeks");
        firstlist.Add("For");
        firstlist.Add("Geeks");
        firstlist.Add("GFG");
        firstlist.Add("C#");
        firstlist.Add("Tutorials");
        firstlist.Add("GeeksforGeeks");

        // Displaying the elements of firstlist
        Console.WriteLine("Elements in List:\n");

        foreach(string ele in firstlist)
        {
            Console.WriteLine(ele);
        }

        // removing 1 elements starting
        // from index 3
        firstlist.RemoveRange(3, 1);

        Console.WriteLine("");

        // Displaying the updated List
        Console.WriteLine("After Removing of elements:\n");

        // Displaying the elements in List
        foreach(string ele in firstlist)
        {
            Console.WriteLine(ele);
        }
    }
}
```

**输出:**

```cs
Elements in List:

Geeks
For
Geeks
GFG
C#
Tutorials
GeeksforGeeks

After Removing of elements:

Geeks
For
Geeks
C#
Tutorials
GeeksforGeeks

```

**例 2:**

```cs
// C# Program to remove a range of
// elements from the List
using System;
using System.Collections;
using System.Collections.Generic;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating an List<T> of Integers
        List<int> firstlist = new List<int>();

        // Adding elements to List
        firstlist.Add(1);
        firstlist.Add(2);
        firstlist.Add(3);
        firstlist.Add(4);
        firstlist.Add(5);
        firstlist.Add(6);
        firstlist.Add(7);

        // Displaying the elements of firstlist
        Console.WriteLine("Elements in List:\n");

        foreach(int ele in firstlist)
        {
            Console.WriteLine(ele);
        }

        // removing 2 elements starting
        // from index 3 i.e 3rd and 4th
        firstlist.RemoveRange(3, 2);

        Console.WriteLine("");

        // Displaying the updated List
        Console.WriteLine("After Removing of elements:\n");

        // Displaying the elements in List
        foreach(int ele in firstlist)
        {
            Console.WriteLine(ele);
        }
    }
}
```

**输出:**

```cs
Elements in List:

1
2
3
4
5
6
7

After Removing of elements:

1
2
3
6
7

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . list-1 . remove range？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.removerange?view=netframework-4.7.2)