# C# 在链表开始处添加新的节点或值

> 原文: [https://www.geeksforgeeks.org/c-sharp-adding-new-node-or-value-at-the-start-of-linkedlistt/](https://www.geeksforgeeks.org/c-sharp-adding-new-node-or-value-at-the-start-of-linkedlistt/)

`LinkedList<T>.AddFirst` 方法用于在链表 `<T>` 的开始处添加一个新的节点或值。此方法的重载列表中有 2 种方法，如下所示:

*   `AddFirst(LinkedListNode<T> node)`
*   `AddFirst(T value)`

## `AddFirst(LinkedListNode<T> node)`

该方法用于在链表 `<T>` 开始处添加指定的新节点。

**语法:**

```cs
public void AddFirst (System.Collections.Generic.LinkedListNode<T> node);
```

在这里，`node` 是新的 `LinkedListNode<T>` 添加在 `LinkedList<T>` 的开始。

**异常:**

*   `ArgumentNullException`: 如果节点为 `null`。
*   `InvalidOperationException`: 如果节点属于另一个链表 `<T>`。

**示例:**

```cs
// C# code to add new node
// at the start of LinkedList
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
        myList.AddLast(6);
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

        // Adding new node at the start of LinkedList
        // This will give error as node is null
        myList.AddFirst(5);

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

> Total nodes in myList are : 6
> 2
> 4
> 6
> 6
> 6
> 8
>
> Unhandled Exception:
> System.ArgumentNullException: Value cannot be null.
> Parameter name: node

**注:**

*   `LinkedList<T>` 接受 `null` 作为引用类型的有效值，并允许重复值。
*   如果 `LinkedList<T>` 为空，新节点将成为第一个和最后一个。
*   这个方法是一个 O(1) 运算。

## `AddFirst(T value)`

该方法用于在链表 `<T>` 开始处添加一个包含指定值的新节点。

**语法:**

```cs
public System.Collections.Generic.LinkedListNode<T> AddFirst (T value);
```

这里，`value` 是 `LinkedList<T>` 开始时要添加的值。

**返回值:** 包含值的新 `LinkedListNode<T>`。

**示例:**

```cs
// C# code to add new node containing
// the specified value at the start
// of LinkedList
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
        myList.AddLast(6);
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

        // Adding new node containing the
        // specified value at the start of LinkedList
        myList.AddFirst(20);

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
Total nodes in myList are : 6
Total nodes in myList are : 7
```

**注:**

*   `LinkedList<T>` 接受 `null` 作为引用类型的有效值，并允许重复值。
*   如果 `LinkedList<T>` 为空，新节点将成为第一个和最后一个。
*   这个方法是一个 O(1) 运算。

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.linkedlist-1.addfirst?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.linkedlist-1.addfirst?view=netframework-4.7.2)