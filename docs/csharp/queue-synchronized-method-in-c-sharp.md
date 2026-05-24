# 排队。C# 中的 Synchronized()方法

> 原文:[https://www . geesforgeks . org/queue-synchronized-method-in-c-sharp/](https://www.geeksforgeeks.org/queue-synchronized-method-in-c-sharp/)

此方法用于返回一个新的队列，该队列包装原始队列并且是线程安全的。此方法返回的包装器在执行操作之前锁定队列，以便以线程安全的方式执行操作。

**语法:**

> 公共静态系统。集合。队列同步(系统。集合.队列队列)；

**返回值:**同步的队列包装器(线程安全)。

**异常:**如果队列为空，这个方法会给出 *ArgumentNullException* 。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to illustrate the
// Queue.Synchronized() Method
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Queue
        Queue myQueue = new Queue();

        // Inserting the elements into the Queue
        myQueue.Enqueue("C");
        myQueue.Enqueue("C++");
        myQueue.Enqueue("Java");
        myQueue.Enqueue("C#");
        myQueue.Enqueue("HTML");
        myQueue.Enqueue("CSS");

        // Creates a synchronized
        // wrapper around the Queue
        Queue sq = Queue.Synchronized(myQueue);

        // Displays the synchronization
        // status of both ArrayList
        Console.WriteLine("myQueue is {0}.", myQueue.IsSynchronized ?
                                "Synchronized" : "Not Synchronized");

        Console.WriteLine("sq is {0}.", sq.IsSynchronized ? 
                      "Synchronized" : "Not Synchronized");
    }
}
```

**输出:**

```cs
myQueue is Not Synchronized.
sq is Synchronized.

```

**例 2:**

```cs
// C# code to illustrate the
// Queue.Synchronized() Method
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Queue
        Queue myQueue = new Queue();

        // Inserting the elements into the Queue
        myQueue.Enqueue("Geeks");
        myQueue.Enqueue("for");
        myQueue.Enqueue("Geeks");
        myQueue.Enqueue("Noida");
        myQueue.Enqueue("Sector");
        myQueue.Enqueue("142");

        // it will give error as
        // the parameter is null
        Queue smyList = Queue.Synchronized(null);
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentNullException:值不能为空。
> 参数名称:队列

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . queue . synchronized？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.queue.synchronized?view=netframework-4.7.2)