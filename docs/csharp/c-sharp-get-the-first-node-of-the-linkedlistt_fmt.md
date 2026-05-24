# C# |获取链表的第一个节点

> 原文：[`https://www.geeksforgeeks.org/c-sharp-get-the-first-node-of-the-linkedlistt/`](https://www.geeksforgeeks.org/c-sharp-get-the-first-node-of-the-linkedlistt/)

`LinkedList<T>` 的 `First` 属性用于获取链表的第一个节点 `<T>`。

## 语法

```cs
public System.Collections.Generic.LinkedListNode First { get; }
```

**返回值：** `LinkedList<T>` 的第一个 `LinkedListNode<T>`。

## 示例

下面给出了一些例子，以便更好地理解实现：

### 示例 1

```cs
// C# code to get the first
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
        myList.AddLast("Geeks");
        myList.AddLast("for");
        myList.AddLast("Data Structures");
        myList.AddLast("Noida");

        // To get the first node of the LinkedList
        if (myList.Count > 0)
            Console.WriteLine(myList.First.Value);
        else
            Console.WriteLine("LinkedList is empty");
    }
}
```

**输出：**

```cs
Geeks 
```

### 示例 2

```cs
// C# code to get the first
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

        // To get the first node of the LinkedList
        if (myList.Count > 0)
            Console.WriteLine(myList.First.Value);
        else
            Console.WriteLine("LinkedList is empty");
    }
}
```

**输出：**

```cs
LinkedList is empty 
```

## 注释

*   `LinkedList` 接受 `null` 值作为引用类型的有效值，并允许重复值。
*   如果链表为空，则 `First` 和 `Last` 属性包含 `null` 值。
*   检索该属性的值是一个 `O(1)` 操作。

## 参考

*   [`https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.linkedlist-1.first?view=netframework-4.7.2`](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.linkedlist-1.first?view=netframework-4.7.2)