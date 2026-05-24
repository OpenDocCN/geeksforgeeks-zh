# C# |删除链接列表开始处的节点

> 原文:[https://www . geeksforgeeks . org/c-sharp-在链接开始时移除节点/T1](https://www.geeksforgeeks.org/c-sharp-removing-the-node-at-the-start-of-the-linkedlistt/)

**链接列表<T1**T5。移除首先方法用于移除链表开始处的节点< T >。

**语法:**

```cs
public void RemoveFirst ();

```

**异常:**如果**链表< **T** >** 为空，该方法抛出 ***无效操作异常*** 。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to remove the node at
// the start of the LinkedList
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

        // Displaying the nodes in LinkedList
        Console.WriteLine("The elements in LinkedList are : ");

        foreach(string str in myList)
        {
            Console.WriteLine(str);
        }

        // Removing the node at the start of LinkedList
        myList.RemoveFirst();

        // Displaying the nodes in LinkedList
        Console.WriteLine("The elements in LinkedList are : ");

        foreach(string str in myList)
        {
            Console.WriteLine(str);
        }
    }
}
```

**输出:**

```cs
The elements in LinkedList are : 
A
B
C
D
E
The elements in LinkedList are : 
B
C
D
E

```

**例 2:**

```cs
// C# code to remove the node at
// the start of the LinkedList
using System;
using System.Collections;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a LinkedList of Integers
        LinkedList<int> myList = new LinkedList<int>();

        // Removing the node at the start of LinkedList
        // This should raise "InvalidOperationException"
        // as the LinkedList is empty
        myList.RemoveFirst();

        // Displaying the nodes in LinkedList
        Console.WriteLine("The elements in LinkedList are : ");

        foreach(int i in myList)
        {
            Console.WriteLine(i);
        }
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。无效操作异常:链接列表为空。

**注:**此法为 **O(1)** 操作。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . linked list-1 . remove first？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.linkedlist-1.removefirst?view=netframework-4.7.2)