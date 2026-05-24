# C# 删除链表末尾的节点

> 原文：[https://www.geeksforgeeks.org/c-sharp-removing-the-node-at-the-end-of-linkedlistt/](https://www.geeksforgeeks.org/c-sharp-removing-the-node-at-the-end-of-linkedlistt/)

`LinkedList<T>` 的 `RemoveLast()` 方法用于删除链表末端的节点。

## 语法

```cs
public void RemoveLast ();
```

## 异常

如果 `LinkedList<T>` 为空，该方法抛出 `InvalidOperationException`。

下面给出了一些例子，以便更好地理解实现：

## 例 1

```cs
// C# code to remove the node at
// the end of the LinkedList
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

        // Removing the node at the end of LinkedList
        myList.RemoveLast();

        // Displaying the nodes in LinkedList
        Console.WriteLine("The elements in LinkedList are : ");

        foreach(string str in myList)
        {
            Console.WriteLine(str);
        }
    }
}
```

输出：

```cs
The elements in LinkedList are : 
A
B
C
D
E
The elements in LinkedList are : 
A
B
C
D
```

## 例 2

```cs
// C# code to remove the node at
// the end of the LinkedList
using System;
using System.Collections;
using System.Collections.Generic;

class GFG {

// Driver code
    public static void Main()
    {
        // Creating a LinkedList of Integers
        LinkedList<int> myList = new LinkedList<int>();

        // Removing the node at the end of LinkedList
        // This should raise "InvalidOperationException"
        // as the LinkedList is empty
        myList.RemoveLast();

        // Displaying the nodes in LinkedList
        Console.WriteLine("The elements in LinkedList are : ");

        foreach(int i in myList)
        {
            Console.WriteLine(i);
        }
    }
}
```

运行时错误：

> 未处理异常:
> System.InvalidOperationException: 链接列表为空。

## 注

此方法为 `O(1)` 操作。

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.linkedlist-1.removelast?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.linkedlist-1.removelast?view=netframework-4.7.2)