# C# |从另一个集合创建队列

> 原文:[https://www . geeksforgeeks . org/c-sharp-create-queue-from-other-collection/](https://www.geeksforgeeks.org/c-sharp-create-a-queue-from-another-collection/)

队列代表一个 ***先进先出*** 集合的对象。当您需要先进先出访问项目时，可以使用它。当您在列表中添加一个项目时，它被称为**入队**，当您移除一个项目时，它被称为**出队**。**排队<t>。用于将队列<t>元素复制到新数组的数组方法</t></t>** 。

**属性:**

*   **Enqueue** Add an element at the end of the queue.
*   **dequeue** Remove the oldest element from the beginning of the queue.
*   **peek** returns the earliest element in the queue, but it will not be removed from the queue.
*   The **capacity** of the queue is the number of elements that the queue can hold.
*   When elements are added to the queue, the capacity will automatically increase as needed by reallocating the internal array.
*   The queue accepts **null** as the valid value of the reference type, and allows duplicate elements.

**语法:**

```cs
public T[] ToArray ();
```

这里 *T[]* 是一个新数组，包含从*队列*复制的元素。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to Create a Queue
// from a collection
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Queue of strings
        Queue<string> myQueue1 = new Queue<string>();

        // Inserting the elements into the Queue
        myQueue1.Enqueue("GeeksforGeeks");
        myQueue1.Enqueue("is");
        myQueue1.Enqueue("the");
        myQueue1.Enqueue("best");
        myQueue1.Enqueue("website");

        // Displaying the count of elements
        // contained in the myQueue1
        Console.Write("Total number of elements in the Queue 1 are : ");

        Console.WriteLine(myQueue1.Count);

        // Displaying the elements in Queue myQueue1
        foreach(string str in myQueue1)
        {
            Console.WriteLine(str);
        }

        // Creating a Queue from a collection
        Queue<string> myQueue2 = new Queue<string>(myQueue1.ToArray());

        // Displaying the count of elements
        // contained in the myQueue2
        Console.Write("Total number of elements in the Queue 2 are : ");

        Console.WriteLine(myQueue2.Count);

        // Displaying the elements in Queue myQueue2
        foreach(string str in myQueue2)
        {
            Console.WriteLine(str);
        }
    }
}
```

**Output:**

```cs
Total number of elements in the Queue 1 are : 5
GeeksforGeeks
is
the
best
website
Total number of elements in the Queue 2 are : 5
GeeksforGeeks
is
the
best
website

```

**例 2:**

```cs
// C# code to Create a Queue
// from a collection
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Queue of Integers
        Queue<int> myQueue1 = new Queue<int>();

        // Inserting the elements into the Queue
        myQueue1.Enqueue(5);
        myQueue1.Enqueue(10);
        myQueue1.Enqueue(15);
        myQueue1.Enqueue(20);
        myQueue1.Enqueue(25);

        // Displaying the count of elements
        // contained in the myQueue1
        Console.Write("Total number of elements in the Queue 1 are : ");

        Console.WriteLine(myQueue1.Count);

        // Displaying the elements in Queue myQueue1
        foreach(int i in myQueue1)
        {
            Console.WriteLine(i);
        }

        // Creating a Queue from a collection
        Queue<int> myQueue2 = new Queue<int>(myQueue1.ToArray());

        // Displaying the count of elements
        // contained in the myQueue2
        Console.Write("Total number of elements in the Queue 2 are : ");

        Console.WriteLine(myQueue2.Count);

        // Displaying the elements in Queue myQueue2
        foreach(int i in myQueue2)
        {
            Console.WriteLine(i);
        }
    }
}
```

**Output:**

```cs
Total number of elements in the Queue 1 are : 5
5
10
15
20
25
Total number of elements in the Queue 2 are : 5
5
10
15
20
25

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . queue-1 . to array？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.queue-1.toarray?view=netframework-4.7.2)