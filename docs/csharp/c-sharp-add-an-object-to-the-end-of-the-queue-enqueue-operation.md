# C# |在队列末端添加对象–入队操作

> 原文:[https://www . geeksforgeeks . org/c-sharp-将对象添加到队列末端-排队-操作/](https://www.geeksforgeeks.org/c-sharp-add-an-object-to-the-end-of-the-queue-enqueue-operation/)

**[队列](https://www.geeksforgeeks.org/queue-data-structure/)** 代表一个 ***先进先出*** 集合的对象。当您需要先进先出访问项目时，可以使用它。当您在列表中添加一个项目时，它被称为**入队**，当您移除一个项目时，它被称为**出队**。

**排队< T >。入队(T)方法**用于将对象添加到队列的末尾< T >。

**属性:**

*   **入队**在队列末尾添加一个元素。
*   **出列**从队列开始处移除最旧的元素。
*   **Peek** 返回队列开始处最早的元素，但不将其从队列中移除。
*   队列的**容量**是队列可以容纳的元素数量。
*   当元素添加到队列中时，容量会根据需要通过重新分配内部阵列来自动增加。
*   队列接受 **null** 作为引用类型的有效值，并允许重复元素。

**语法:**

```cs
void Enqueue(object obj);

```

Enqueue()方法在队列的末尾插入值。

**示例:**

```cs
// C# code to add an object
// to the end of the Queue
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Queue of strings
        Queue<string> myQueue = new Queue<string>();

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

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . queue-1 . enqueue？view = net framework-4 . 7 . 2 # System _ Collections _ Generic _ Queue _ 1 _ Enqueue _ 0 _](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.queue-1.enqueue?view=netframework-4.7.2# System_Collections_Generic_Queue_1_Enqueue__0_)