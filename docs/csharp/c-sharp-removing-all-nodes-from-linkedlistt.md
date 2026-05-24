# C# |从链接列表中删除所有节点

> 原文:[https://www . geeksforgeeks . org/c-sharp-remove-all-nodes-from-linked list/](https://www.geeksforgeeks.org/c-sharp-removing-all-nodes-from-linkedlistt/)

**链接列表<T1**T5。清除方法用于从链表中移除所有节点< T >。

**语法:**

```cs
public void Clear ();

```

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to remove all
// nodes from LinkedList
using System;
using System.Collections;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a LinkedList of Strings
        LinkedList<String> myList = new LinkedList<String>();

        // Adding nodes in LinkedList
        myList.AddLast("A");
        myList.AddLast("B");
        myList.AddLast("C");
        myList.AddLast("D");
        myList.AddLast("E");

        // To get the count of nodes in LinkedList
        // before removing all the nodes
        Console.WriteLine("Total nodes in myList are : " + myList.Count);

        // Removing all nodes from LinkedList
        myList.Clear();

        // To get the count of nodes in LinkedList
        // after removing all the nodes
        Console.WriteLine("Total nodes in myList are : " + myList.Count);
    }
}
```

**输出:**

```cs
Total nodes in myList are : 5
Total nodes in myList are : 0

```

**例 2:**

```cs
// C# code to remove all
// nodes from LinkedList
using System;
using System.Collections;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a LinkedList of Integers
        LinkedList<int> myList = new LinkedList<int>();

        // Adding nodes in LinkedList
        myList.AddLast(2);
        myList.AddLast(4);
        myList.AddLast(6);

        // To get the count of nodes in LinkedList
        // before removing all the nodes
        Console.WriteLine("Total nodes in myList are : " + myList.Count);

        // Removing all nodes from LinkedList
        myList.Clear();

        // To get the count of nodes in LinkedList
        // after removing all the nodes
        Console.WriteLine("Total nodes in myList are : " + myList.Count);
    }
}
```

**输出:**

```cs
Total nodes in myList are : 3
Total nodes in myList are : 0

```

**注:**

*   **Count** 设置为零，集合元素对其他对象的引用也会被释放。
*   **第一个**和**最后一个**设置为**空**。
*   这个方法是一个 **O(n)** 运算，其中 n 是 Count。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . linked list-1 . clear？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.linkedlist-1.clear?view=netframework-4.7.2)