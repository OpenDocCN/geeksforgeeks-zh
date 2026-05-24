# C# |获取 LinkedList 中包含的节点数

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-in-linked list 中包含的节点数/](https://www.geeksforgeeks.org/c-sharp-get-the-number-of-nodes-contained-in-linkedlistt/)

**链接列表<T1**T5。Count 属性用于获取 LinkedList < T >中实际包含的节点数。

**语法:**

```cs
public int Count { get; }

```

**返回值:**链表中实际包含的节点数。

**注意:**检索该属性的值是一个 O(1)运算。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to get the number
// of nodes actually contained
// in the LinkedList
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
        myList.AddLast("Geeks");
        myList.AddLast("for");
        myList.AddLast("Data Structures");
        myList.AddLast("Noida");

        // To get the number of nodes actually
        // contained in the LinkedList
        if (myList.Count > 0)
            Console.WriteLine(myList.Count);
        else
            Console.WriteLine("LinkedList is empty");
    }
}
```

**输出:**

```cs
4

```

**例 2 :**

```cs
// C# code to get the number
// of nodes actually contained
// in the LinkedList
using System;
using System.Collections;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a LinkedList of Integers
        LinkedList<int> myList = new LinkedList<int>();

        // To get the number of nodes actually
        // contained in the LinkedList
        if (myList.Count > 0)
            Console.WriteLine(myList.Count);
        else
            Console.WriteLine("LinkedList is empty");
    }
}
```

输出:

```cs
LinkedList is empty

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . linked list-1 . count？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.linkedlist-1.count?view=netframework-4.7.2)