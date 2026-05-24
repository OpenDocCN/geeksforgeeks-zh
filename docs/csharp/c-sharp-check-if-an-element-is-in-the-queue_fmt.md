# C# |检查队列中是否有元素

> 原文：[https://www.geeksforgeeks.org/c-sharp-check-if-an-element-is-in-the-queue/](https://www.geeksforgeeks.org/c-sharp-check-if-an-element-is-in-the-queue/)

`Queue` 代表一个先进先出集合的对象。当您需要先进先出访问项目时，可以使用它。当您在列表中添加一个项目时，它被称为**入队**，当您移除一个项目时，它被称为**出队**。`Queue<T>.Contains(T)` 方法用于检查一个元素是否在队列中。

## 属性

*   `Enqueue`：在队列末尾添加一个元素。
*   `Dequeue`：从队列开头移除最旧的元素。
*   `Peek`：返回队列开头的最早元素，但不会将其从队列中移除。
*   队列的 `Capacity` 是队列可以容纳的元素数量。
*   当向队列添加元素时，容量会通过重新分配内部数组按需自动增加。
*   队列接受 `null` 值作为引用类型的有效值，并允许重复元素。

## 语法

```csharp
public virtual bool Contains(object obj);
```

## 返回值

如果元素存在于队列中，函数返回 `true`，如果元素不存在于队列中，函数返回 `false`。

下面给出了一些例子，以便更好地理解实现：

## 例 1

```csharp
// C# code to Check if a Queue
// contains an element
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Queue of Integers
        Queue<int> myQueue = new Queue<int>();

        // Inserting the elements into the Queue
        myQueue.Enqueue(5);
        myQueue.Enqueue(10);
        myQueue.Enqueue(15);
        myQueue.Enqueue(20);
        myQueue.Enqueue(25);

        // Checking whether the element is
        // present in the Queue or not
        // The function returns True if the
        // element is present in the Queue, else
        // returns False
        Console.WriteLine(myQueue.Contains(7));
    }
}
```

**输出：**

```csharp
False
```

## 例 2

```csharp
// C# code to Check if a Queue
// contains an element
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Queue of strings
        Queue<string> myQueue = new Queue<string>();

        // Inserting the elements into the Queue
        myQueue.Enqueue("Geeks");
        myQueue.Enqueue("Geeks Classes");
        myQueue.Enqueue("Noida");
        myQueue.Enqueue("Data Structures");
        myQueue.Enqueue("GeeksforGeeks");

        // Checking whether the element is
        // present in the Queue or not
        // The function returns True if the
        // element is present in the Queue, else
        // returns False
        Console.WriteLine(myQueue.Contains("GeeksforGeeks"));
    }
}
```

**输出：**

```csharp
True
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.queue-1.contains?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.queue-1.contains?view=netframework-4.7.2)