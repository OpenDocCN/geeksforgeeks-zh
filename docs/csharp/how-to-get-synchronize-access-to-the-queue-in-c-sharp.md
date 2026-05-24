# 如何在 C# 中同步访问队列

> 原文:[https://www . geeksforgeeks . org/如何同步访问 c-sharp 中的队列/](https://www.geeksforgeeks.org/how-to-get-synchronize-access-to-the-queue-in-c-sharp/)

**排队。同步根属性**用于获取一个对象，该对象可用于同步对队列的访问。队列表示对象的先进先出集合。当您需要先进先出访问项目时，可以使用它。当您在列表中添加一个项目时，它被称为入队，当您移除一个项目时，它被称为出列。这个类属于`System.Collections`命名空间，实现了 ICollection、IEnumerable 和 ICloneable 接口。

**要点:**

*   完成对象同步后，只有一个线程可以操作队列中的数据。
*   属性是提供读取、写入和计算私有数据字段的方法的类的成员。
*   同步代码不能直接在集合上执行，因此它必须在集合的同步根上执行操作，以保证从其他对象派生的集合的正确操作。
*   检索该属性的值是一个 O(1)操作。

> **语法:**公共虚拟对象 SyncRoot { get}
> 
> **属性值:**可用于同步队列访问的对象。

**示例 1:** 在这段代码中，我们使用 SyncRoot 来获得名为 *q1* 的队列的同步访问，这不是一个线程安全的过程，可能会导致异常。所以为了避免异常，我们在枚举期间锁定集合。

```cs
// C# program to illustrate the
// use of SyncRoot property of
// the Queue
using System;
using System.Threading;
using System.Collections;

namespace sync_root {

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Declaring an Queue
        Queue q1 = new Queue();

        // Adding elements to Queue
        q1.Enqueue(1);
        q1.Enqueue(2);
        q1.Enqueue(3);
        q1.Enqueue(4);
        q1.Enqueue(5);

        // Using the SyncRoot property
        lock(q1.SyncRoot)
        {
            // foreach loop to display
            // the elements in q1
            foreach(Object i in q1)
                Console.WriteLine(i);
        }
    }
}
}
```

**Output:**

```cs
1
2
3
4
5

```

**例 2:**

```cs
// C# program to illustrate the
// use of SyncRoot property of
// the Queue
using System;
using System.Threading;
using System.Collections;

namespace sync_root {

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Declaring an Queue
        Queue q1 = new Queue();

        // Adding elements to Queue
        q1.Enqueue("C");
        q1.Enqueue("C++");
        q1.Enqueue("Java");
        q1.Enqueue("C#");
        q1.Enqueue("HTML");

        // Using the SyncRoot property
        lock(q1.SyncRoot)
        {
            // foreach loop to display
            // the elements in q1
            foreach(Object i in q1)
                Console.WriteLine(i);
        }
    }
}
}
```

**Output:**

```cs
C
C++
Java
C#
HTML

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . queue . sync root？view = net framework-4 . 7 . 2 # System _ Collections _ Queue _ SyncRoot](https://docs.microsoft.com/en-us/dotnet/api/system.collections.queue.syncroot?view=netframework-4.7.2# System_Collections_Queue_SyncRoot)