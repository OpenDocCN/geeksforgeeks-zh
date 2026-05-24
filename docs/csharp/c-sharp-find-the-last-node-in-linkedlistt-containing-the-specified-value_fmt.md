# C# 查找 LinkedList<T> 中包含指定值的最后一个节点

> 原文: [https://www.geeksforgeeks.org/c-sharp-find-the-last-node-in-linkedlistt-containing-the-specified-value/](https://www.geeksforgeeks.org/c-sharp-find-the-last-node-in-linkedlistt-containing-the-specified-value/)

`LinkedList<T>.FindLast(T)` 方法用于查找包含指定值的最后一个节点。

## 语法

```cs
public System.Collections.Generic.LinkedListNode<T> FindLast (T value);
```

这里，`value` 是链表中要定位的值。

## 返回值

该方法返回最后一个包含指定值的 `LinkedListNode<T>`，否则，`null`。

下面给出了一些例子，以便更好地理解实现:

## 例 1

```cs
// C# code to find the last node
// that contains the specified value
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

        // Finding the last node that
        // contains the specified value
        LinkedListNode<String> temp = myList.FindLast("D");

        Console.WriteLine(temp.Value);
    }
}
```

## 输出

```cs
D
```

## 例 2

```cs
// C# code to find the last node
// that contains the specified value
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
        myList.AddLast(5);
        myList.AddLast(7);
        myList.AddLast(9);
        myList.AddLast(11);
        myList.AddLast(12);

        // Finding the last node that
        // contains the specified value
        LinkedListNode<int> temp = myList.FindLast(2);

        Console.WriteLine(temp.Value);
    }
}
```

## 运行时错误

> 未处理异常:
> System.NullReferenceException: 对象引用未设置为对象的实例

## 注

*   从**最后一个**开始向后搜索链表，并在**第一个**结束。
*   此方法执行线性搜索。因此，这个方法是一个 `O(n)` 运算，其中 `n` 是 `Count`。

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.linkedlist-1.findlast?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.linkedlist-1.findlast?view=netframework-4.7.2)