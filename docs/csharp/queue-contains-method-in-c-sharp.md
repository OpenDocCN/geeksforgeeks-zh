# 排队。在 C# 中包含()方法

> 原文:[https://www . geesforgeks . org/queue-contains-method-in-c-sharp/](https://www.geeksforgeeks.org/queue-contains-method-in-c-sharp/)

此方法用于检查元素是否在队列中。这个方法执行线性搜索，因此，这个方法是一个 O(n)运算，其中 n 是 Count。这种方法属于系统。集合命名空间。

**语法:**

```cs
public virtual bool Contains(object obj);
```

这里， *obj* 是要在队列中定位的对象。该值可以为空。

**返回值:**如果元素存在于队列中，函数返回**真**，如果元素不存在于队列中，函数返回**假**。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

## c#

```cs
// C# code to illustrate the
// Queue.Contains() Method
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Queue
        Queue myQueue = new Queue<int>();

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

**输出:**

```cs
False
```

**例 2:**

## c#

```cs
// C# code to illustrate the
// Queue.Contains() Method
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Queue of strings
        Queue myQueue = new Queue();

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

**输出:**

```cs
True
```

**参考:**

*   [https://docs。微软。com/en-us/dotnet/API/system。收藏品。排队。包含？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.queue.contains?view=netframework-4.7.2)