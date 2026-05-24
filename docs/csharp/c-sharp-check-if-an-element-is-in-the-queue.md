# C# |检查队列中是否有元素

> 原文:[https://www . geeksforgeeks . org/c-sharp-检查一个元素是否在队列中/](https://www.geeksforgeeks.org/c-sharp-check-if-an-element-is-in-the-queue/)

**[队列](https://www.geeksforgeeks.org/queue-data-structure/)** 代表一个 ***先进先出*** 集合的对象。当您需要先进先出访问项目时，可以使用它。当您在列表中添加一个项目时，它被称为**入队**，当您移除一个项目时，它被称为**出队**。**排队<t>。Contains(T)方法</t>** 用于检查一个元素是否在队列<t>中。</t>

**属性:**

*   **Enqueue** Add an element at the end of the queue.
*   **dequeue** Remove the oldest element from the beginning of the queue.
*   **peek** Returns the earliest element at the beginning of the queue, but it will not be removed from the queue.
*   The **capacity** of the queue is the number of elements that the queue can hold.
*   When elements are added to the queue, the capacity will automatically increase as needed by reallocating the internal array.
*   The queue accepts **null value** as valid value of reference type, and allows duplicate elements.

**语法:**

```cs
public virtual bool Contains(object obj);

```

**返回值:**如果元素存在于队列中，函数返回**真**，如果元素不存在于队列中，函数返回**假**。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
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

**Output:**

```cs
False

```

**例 2:**

```cs
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

**Output:**

```cs
True

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . queue-1 . contains？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.queue-1.contains?view=netframework-4.7.2)