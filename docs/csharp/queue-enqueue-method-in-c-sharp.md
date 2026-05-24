# 排队。C# 中的 Enqueue()方法

> 原文:[https://www . geesforgeks . org/queue-enqueue-method-in-c-sharp/](https://www.geeksforgeeks.org/queue-enqueue-method-in-c-sharp/)

此方法用于将对象添加到队列的末尾。这属于系统。集合命名空间。该值可以为空，如果计数小于内部数组的容量，则该方法是一个 0(1)操作。如果需要重新分配内部数组来容纳新元素，这个方法就变成了 O(n)运算，其中 n 是 Count。
**语法:**

```cs
public virtual void Enqueue (object obj);
```

这里， *obj* 是添加到队列中的对象。
**例:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# code to illustrate the
// Queue.Enqueue() Method
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Queue
        Queue myQueue = new Queue();

        // Inserting the elements into the Queue
        myQueue.Enqueue("one");

        // Displaying the count of elements
        // contained in the Queue
        Console.Write("Total number of elements in the Queue are : ");

        Console.WriteLine(myQueue.Count);

        myQueue.Enqueue("two");

        // Displaying the count of elements
        // contained in the Queue
        Console.Write("Total number of elements in the Queue are : ");

        Console.WriteLine(myQueue.Count);

        myQueue.Enqueue("three");

        // Displaying the count of elements
        // contained in the Queue
        Console.Write("Total number of elements in the Queue are : ");

        Console.WriteLine(myQueue.Count);

        myQueue.Enqueue("four");

        // Displaying the count of elements
        // contained in the Queue
        Console.Write("Total number of elements in the Queue are : ");

        Console.WriteLine(myQueue.Count);

        myQueue.Enqueue("five");

        // Displaying the count of elements
        // contained in the Queue
        Console.Write("Total number of elements in the Queue are : ");

        Console.WriteLine(myQueue.Count);

        myQueue.Enqueue("six");

        // Displaying the count of elements
        // contained in the Queue
        Console.Write("Total number of elements in the Queue are : ");

        Console.WriteLine(myQueue.Count);
    }
}
```

**Output:** 

```cs
Total number of elements in the Queue are : 1
Total number of elements in the Queue are : 2
Total number of elements in the Queue are : 3
Total number of elements in the Queue are : 4
Total number of elements in the Queue are : 5
Total number of elements in the Queue are : 6
```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . queue . enqueue？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.queue.enqueue?view=netframework-4.7.2)