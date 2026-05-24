# 排队。是 C# 中的同步属性

> 原文:[https://www . geesforgeks . org/queue-is synchronized-property-in-c-sharp/](https://www.geeksforgeeks.org/queue-issynchronized-property-in-c-sharp/)

此属性用于获取一个值，该值指示对队列的访问是否同步(线程安全)。

**语法:**

```cs
public virtual bool IsSynchronized { get; }
```

**属性值:**如果对队列的访问是同步的(线程安全的)，则该属性返回 *true* ，否则返回 false。默认值为 false。

以下程序说明了上述属性的使用:

**例 1:**

```cs
// C# code to illustrate the
// Queue.IsSynchronized Property
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
        // status of both Queue
        Console.WriteLine("myQueue is {0}.", myQueue.IsSynchronized ?
                                "Synchronized" : "Not Synchronized");

        Console.WriteLine("sq is {0}.", sq.IsSynchronized ? 
                       "Synchronized" : "Not Synchronized");
    }
}
```

**Output:**

```cs
myQueue is Not Synchronized.
sq is Synchronized.

```

**例 2:**

```cs
// C# code to check if Queue
// Is Synchronized or not
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Queue
        Queue myQueue = new Queue();

        // Inserting the elements into the Queue
        myQueue.Enqueue(1);
        myQueue.Enqueue(2);
        myQueue.Enqueue(3);
        myQueue.Enqueue(4);

        // the default is false for
        // IsSynchronized property
        Console.WriteLine(myQueue.IsSynchronized);
    }
}
```

**Output:**

```cs
False

```

**注:**

*   检索该属性的值是一个 O(1)操作。
*   为了保证队列的线程安全，所有操作都必须通过 Synchronized 方法返回的包装器来完成。
*   枚举集合本质上不是线程安全的过程。即使同步了集合，其他线程仍然可以修改集合，这将导致枚举数引发异常。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . queue . is synchronized？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.queue.issynchronized?view=netframework-4.7.2)