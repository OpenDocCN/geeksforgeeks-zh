# C# |从列表中删除所有元素

> 原文:[https://www . geesforgeks . org/c-sharp-从列表中删除所有元素/](https://www.geeksforgeeks.org/c-sharp-removing-all-the-elements-from-the-list/)

**列表**类表示可通过索引访问的对象列表。它属于*体系。集合.泛型*命名空间。List 类可以用来创建不同类型的集合，如整数、字符串等。列表类还提供了搜索、排序和操作列表的方法。**名单。清除方法**用于从列表中移除所有元素。

**属性:**

*   它不同于数组。一个**列表可以动态调整大小**但是数组不能。
*   列表类可以接受 null 作为引用类型的有效值，并且它**也允许重复元素**。
*   如果计数等于容量，则列表的容量会通过重新分配内部阵列而自动增加。在添加新元素之前，现有元素将被复制到新数组中。

**语法:**

```cs
public void Clear ();
```

以下程序说明了如何从列表中删除所有元素:

**例 1:**

```cs
// C# program to remove all the
// elements from a List
using System;
using System.Collections.Generic;

class Geeks {

    // Main Method
    public static void Main()
    {

        // Creating a List of integers
        List<int> list1 = new List<int>();

        // Inserting the elements into the List
        list1.Add(1);
        list1.Add(4);
        list1.Add(3);
        list1.Add(1);
        list1.Add(2);

        // Displaying the count of elements
        // contained in the List before
        // removing all the elements
        Console.Write("Number of elements in the List Before Removing: ");

        // using Count property
        Console.WriteLine(list1.Count);

        // Removing all elements from list
        list1.Clear();

        // Displaying the count of elements
        // contained in the List after
        // removing all the elements
        Console.Write("Number of elements in the List After Removing: ");

        // using Count property
        Console.WriteLine(list1.Count);
    }
}
```

**输出:**

```cs
Number of elements in the List Before Removing: 5
Number of elements in the List After Removing: 0

```

**例 2:**

```cs
// C# program to remove all the
// elements from a List
using System;
using System.Collections.Generic;

class Geeks {

    // Main Method
    public static void Main()
    {

        // Creating a List of strings
        List<string> list1 = new List<string>();

        // Inserting the elements into the List
        list1.Add("Welcome");
        list1.Add("To");
        list1.Add("Geeks");
        list1.Add("for");
        list1.Add("Geeks");
        list1.Add("Geeks");
        list1.Add("Geeks");

        // Displaying the count of elements
        // contained in the List before
        // removing all the elements
        Console.Write("Number of elements in the List Before Removing: ");

        // using Count property
        Console.WriteLine(list1.Count);

        // Removing all elements from list
        list1.Clear();

        // Displaying the count of elements
        // contained in the List after
        // removing all the elements
        Console.Write("Number of elements in the List After Removing: ");

        // using Count property
        Console.WriteLine(list1.Count);
    }
}
```

**输出:**

```cs
Number of elements in the List Before Removing: 7
Number of elements in the List After Removing: 0

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . list-1 . clear？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.clear?view=netframework-4.7.2)