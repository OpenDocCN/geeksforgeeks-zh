# 在 C# 中获取队列开头的对象

> 原文:[https://www . geeksforgeeks . org/在 c-sharp 队列开始处获取对象/](https://www.geeksforgeeks.org/getting-an-object-at-the-beginning-of-the-queue-in-c-sharp/)

**出列()**方法用于返回队列开头的对象。该方法类似于 Peek()方法。出列和查看方法的唯一区别是，查看()方法不会修改队列，但出列会修改。这个方法是一个 O(1)操作，属于`System.Collections.Generic`命名空间。

**语法:**

```cs
public T Dequeue ();

```

**返回值:**返回从队列开头删除的对象。

**异常:**该方法在调用空队列时抛出*无效操作异常*，因此在调用出列()方法之前，请始终检查队列的总计数是否大于零。

以下程序说明了上述方法的使用:

```cs
// C# Program to illustrate the use
// of Queue<T>.Dequeue Method
using System;
using System.Collections.Generic;

class GFG {

    // Main Method
    public static void Main()
    {

        // creating a queue of integers
        Queue<int> queue = new Queue<int>();
        queue.Enqueue(3);
        queue.Enqueue(2);
        queue.Enqueue(1);
        queue.Enqueue(4);

        Console.WriteLine("Number of elements in the Queue: {0}",
                                                   queue.Count);

        // Retrieveing top element of queue
        Console.WriteLine("Top element of queue is:");
        Console.WriteLine(queue.Dequeue());

        // printing the no of queue element
        // after dequeue operation
        Console.WriteLine("Number of elements in the Queue: {0}",
                                                   queue.Count);
    }
}
```

**Output:**

```cs
Number of elements in the Queue: 4
Top element of queue is:
3
Number of elements in the Queue: 3

```

**例 2:**

```cs
// C# Program to illustrate the use
// of Queue<T>.Dequeue Method
using System;
using System.Collections.Generic;

class GFG {

    // Main Method
    public static void Main()
    {
        Queue<int> queue = new Queue<int>();

        // Adding elements in Queue
        queue.Enqueue(2);
        queue.Enqueue(5);

        Console.WriteLine("Number of elements in the Queue: {0}",
                                                    queue.Count);

        // Retrieveing top element of queue
        Console.WriteLine("Top element of queue is:");
        Console.WriteLine(queue.Dequeue());

        // printing the no. of queue element
        // after dequeue operation
        Console.WriteLine("Number of elements in the Queue: {0}",
                                                   queue.Count);
    }
}
```

**Output:**

```cs
Number of elements in the Queue: 2
Top element of queue is:
2
Number of elements in the Queue: 1

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . queue-1 .出列？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.queue-1.dequeue?view=netframework-4.7.2)