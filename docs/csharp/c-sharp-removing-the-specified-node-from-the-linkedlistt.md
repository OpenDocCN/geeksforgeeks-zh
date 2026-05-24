# C# |从链接列表中删除指定节点

> 原文:[https://www . geeksforgeeks . org/c-sharp-从链接中移除指定的节点 istt/](https://www.geeksforgeeks.org/c-sharp-removing-the-specified-node-from-the-linkedlistt/)

**Remove(linked list node<**T**>)**方法用于从 LinkedList < **T** >中删除指定节点。

**语法:**

```cs
public void Remove (System.Collections.Generic.LinkedListNode<T> node);

```

在这里， ***节点*** 是要从链表< **中删除的链表节点<**T**>>。**

**异常:**

*   **ArgumentNullException :** 如果节点为空。
*   **无效操作异常:**如果节点不在当前链接列表中< **T** >。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to remove the specified
// node from the LinkedList
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
        myList.AddLast(8);

        // To get the count of nodes in LinkedList
        // before removing all the nodes
        Console.WriteLine("Total nodes in myList are : " + myList.Count);

        // Displaying the nodes in LinkedList
        foreach(int i in myList)
        {
            Console.WriteLine(i);
        }

        // Removing the first node from the LinkedList
        myList.Remove(myList.First);

        // To get the count of nodes in LinkedList
        // after removing all the nodes
        Console.WriteLine("Total nodes in myList are : " + myList.Count);

        // Displaying the nodes in LinkedList
        foreach(int i in myList)
        {
            Console.WriteLine(i);
        }
    }
}
```

**输出:**

```cs
Total nodes in myList are : 4
2
4
6
8
Total nodes in myList are : 3
4
6
8

```

**例 2:**

```cs
// C# code to remove the specified
// node from the LinkedList
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

        // Displaying the nodes in LinkedList
        foreach(string str in myList)
        {
            Console.WriteLine(str);
        }

        // Removing the specified node from the LinkedList
        myList.Remove("D");

        // To get the count of nodes in LinkedList
        // after removing all the nodes
        Console.WriteLine("Total nodes in myList are : " + myList.Count);

        // Displaying the nodes in LinkedList
        foreach(string str in myList)
        {
            Console.WriteLine(str);
        }
    }
}
```

**输出:**

```cs
Total nodes in myList are : 5
A
B
C
D
E
Total nodes in myList are : 4
A
B
C
E

```

**注:**此方法为 O(1)运算。

**参考:**

[https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . linked list-1 . remove？view = net framework-4 . 7 . 2 # System _ Collections _ Generic _ LinkedList _ 1 _ Remove _ System _ Collections _ Generic _ LinkedListNode _ 0 _ _](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.linkedlist-1.remove?view=netframework-4.7.2# System_Collections_Generic_LinkedList_1_Remove_System_Collections_Generic_LinkedListNode__0__)