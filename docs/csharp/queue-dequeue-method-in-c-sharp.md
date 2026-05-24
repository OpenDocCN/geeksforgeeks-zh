# 排队。C# 中的出列方法

> 原文:[https://www . geesforgeks . org/queue-queue-method-in-c-sharp/](https://www.geeksforgeeks.org/queue-dequeue-method-in-c-sharp/)

**出列()**方法用于返回队列开头的对象。该方法类似于 Peek()方法。出列和查看方法的唯一区别是，查看()方法不会修改队列，但出列会修改。这个方法是一个 O(1)操作，属于`System.Collections`命名空间。

**语法:**

```cs
public virtual object Dequeue ();

```

**返回值:**返回从队列开头删除的对象。

**异常:**该方法在调用空队列时抛出*无效操作异常*，因此在调用出列()方法之前，请始终检查队列的总计数是否大于零。

以下程序说明了上述方法的使用:

```cs
// C# Program to illustrate the use 
// of Queue.Dequeue Method
using System;
using System.Collections;

class GFG {

    // Main Method
    public static void Main()
    {
        Queue queue = new Queue();
        queue.Enqueue(3);
        queue.Enqueue(2);
        queue.Enqueue(1);
        queue.Enqueue("Four");

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

```cs
// C# Program to illustrate the use 
// of Queue.Dequeue Method
using System;
using System.Collections;

class GFG {

    // Main Method
    public static void Main()
    {
        Queue queue = new Queue();

        // Adding elements in Queue
        queue.Enqueue(2);
        queue.Enqueue("Four");

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

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . queue .出列？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.queue.dequeue?view=netframework-4.7.2)