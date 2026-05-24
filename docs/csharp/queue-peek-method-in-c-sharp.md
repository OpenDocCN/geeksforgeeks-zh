# 排队。C# 中的 Peek 方法

> 原文:[https://www.geeksforgeeks.org/queue-peek-method-in-c-sharp/](https://www.geeksforgeeks.org/queue-peek-method-in-c-sharp/)

此方法返回队列开头的对象，而不移除它。此方法类似于出列方法，但 Peek 不修改队列，是一个 O(1)操作。该方法属于*系统。集合*命名空间。

**语法:**

```cs
public virtual object Peek ();
```

**返回值:**队列开头的对象。

**异常:**如果*队列*为空，此方法将给出*无效操作异常*。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to illustrate the
// Queue.Peek Method
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Queue
        Queue myQueue = new Queue();

        // Inserting the elements into the Queue
        myQueue.Enqueue("1st Element");
        myQueue.Enqueue("2nd Element");
        myQueue.Enqueue("3rd Element");
        myQueue.Enqueue("4th Element");
        myQueue.Enqueue("5th Element");
        myQueue.Enqueue("6th Element");

        // Displaying the count of elements
        // contained in the Queue
        Console.Write("Total number of elements in the Queue are : ");

        Console.WriteLine(myQueue.Count);

        // Displaying the beginning element of Queue
        // without removing it from the Queue
        Console.WriteLine("Element at the beginning is : " 
                                        + myQueue.Peek());

        // Displaying the beginning element of Queue
        // without removing it from the Queue
        Console.WriteLine("Element at the beginning is : " 
                                        + myQueue.Peek());

        // Displaying the count of elements
        // contained in the Queue
        Console.Write("Total number of elements in the Queue are : ");

        Console.WriteLine(myQueue.Count);
    }
}
```

**输出:**

```cs
Total number of elements in the Queue are : 6
Element at the beginning is : 1st Element
Element at the beginning is : 1st Element
Total number of elements in the Queue are : 6

```

**例 2:**

```cs
// C# code to illustrate the
// Queue.Peek Method
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Queue
        Queue myQueue = new Queue();

        // Displaying the beginning element of Queue
        // without removing it from the Queue
        // Calling Peek() method on empty Queue
        // will throw InvalidOperationException.
        Console.WriteLine("Element at the beginning is : "
                                       + myQueue.Peek());
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。无效操作异常:队列为空。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . queue . peek？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.queue.peek?view=netframework-4.7.2)