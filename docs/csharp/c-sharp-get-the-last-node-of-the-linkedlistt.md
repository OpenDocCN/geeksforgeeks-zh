# C# |获取链表的最后一个节点

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-the-linked list/最后一个节点](https://www.geeksforgeeks.org/c-sharp-get-the-last-node-of-the-linkedlistt/)

**链接列表<T1**T5。Last 属性用于获取链表的最后一个节点< T >。

**语法:**

```cs
public System.Collections.Generic.LinkedListNode Last { get; }

```

**返回值:**链接列表*<**的最后一个*链接列表节点<**>*****T>*******。**

**下面给出了一些例子，以便更好地理解实现:**

****例 1:****

```cs
// C# code to get the last
// node of the LinkedList
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

        // To get the last node of the LinkedList
        if (myList.Count > 0)
            Console.WriteLine(myList.Last.Value);
        else
            Console.WriteLine("LinkedList is empty");
    }
}
```

****输出:****

```cs
E 
```

****例 2:****

```cs
// C# code to get the last
// node of the LinkedList
using System;
using System.Collections;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a LinkedList of Integers
        LinkedList<int> myList = new LinkedList<int>();

        // To get the last node of the LinkedList
        if (myList.Count > 0)
            Console.WriteLine(myList.Last.Value);
        else
            Console.WriteLine("LinkedList is empty");
    }
}
```

****输出:****

```cs
LinkedList is empty 
```

****注:****

*   **链接列表接受**空值**作为引用类型的有效值，并允许重复值。**
*   **如果链接列表为空，则**第一个**和**最后一个**属性包含**空值**。**
*   **检索该属性的值是一个 **O(1)** 操作。**

****参考:****

*   **[https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . linked list-1 . last？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.linkedlist-1.last?view=netframework-4.7.2)**