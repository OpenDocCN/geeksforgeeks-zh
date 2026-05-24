# C# |从队列中移除所有对象

> 原文:[https://www . geesforgeks . org/c-sharp-从队列中移除所有对象/](https://www.geeksforgeeks.org/c-sharp-remove-all-objects-from-the-queue/)

[队列](https://www.geeksforgeeks.org/queue-data-structure/)代表一个 ***先进先出*** 集合的对象。当您需要先进先出访问项目时，可以使用它。当您在列表中添加一个项目时，它被称为**入队**，当您移除一个项目时，它被称为**出队**。**排队<t>。清除方法</t>** 用于从队列<t>中移除对象。该方法为 *O(n)* 运算，其中 *n* 为元素总数。</t>

**属性:**

*   **Enqueue** Add an element at the end of the queue.
*   **dequeue** Remove the oldest element from the beginning of the queue.
*   **peek** returns the earliest element in the queue, but it is not removed from the queue.
*   The **capacity** of the queue is the number of elements that the queue can hold.
*   When elements are added to the queue, the capacity will automatically increase as needed by reallocating the internal array.
*   The queue accepts **null value** as valid value of reference type, and allows duplicate elements.

**语法:**

```cs
public virtual void Clear();

```

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to Remove all
// objects from the Queue
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Queue of strings
        Queue<string> myQueue = new Queue<string>();

        // Inserting the elements into the Queue
        myQueue.Enqueue("1st Element");
        myQueue.Enqueue("2nd Element");
        myQueue.Enqueue("3rd Element");
        myQueue.Enqueue("4th Element");
        myQueue.Enqueue("5th Element");
        myQueue.Enqueue("6th Element");

        // Displaying the count of elements
        // contained in the Queue before
        // removing all the elements
        Console.Write("Total number of elements in the Queue are : ");

        Console.WriteLine(myQueue.Count);

        // Removing all elements from Queue
        myQueue.Clear();

        // Displaying the count of elements
        // contained in the Queue after
        // removing all the elements
        Console.Write("Total number of elements in the Queue are : ");

        Console.WriteLine(myQueue.Count);
    }
}
```

**Output:**

```cs
Total number of elements in the Queue are : 6
Total number of elements in the Queue are : 0

```

**例 2:**

```cs
// C# code to Remove all
// objects from the Queue
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Queue of Integers
        Queue<int> myQueue = new Queue<int>();

        // Inserting the elements into the Queue
        myQueue.Enqueue(3);
        myQueue.Enqueue(5);
        myQueue.Enqueue(7);
        myQueue.Enqueue(9);
        myQueue.Enqueue(11);

        // Displaying the count of elements
        // contained in the Queue before
        // removing all the elements
        Console.Write("Total number of elements in the Queue are : ");

        Console.WriteLine(myQueue.Count);

        // Removing all elements from Queue
        myQueue.Clear();

        // Displaying the count of elements
        // contained in the Queue after
        // removing all the elements
        Console.Write("Total number of elements in the Queue are : ");

        Console.WriteLine(myQueue.Count);
    }
}
```

**Output:**

```cs
Total number of elements in the Queue are : 5
Total number of elements in the Queue are : 0

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . queue-1 . clear？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.queue-1.clear?view=netframework-4.7.2)