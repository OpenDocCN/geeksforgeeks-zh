# C# |获取队列开头的对象–Peek 操作

> 原文:[https://www . geesforgeks . org/c-sharp-在队列开始时获取对象-peek-operation/](https://www.geeksforgeeks.org/c-sharp-get-the-object-at-the-beginning-of-the-queue-peek-operation/)

**[队列](https://www.geeksforgeeks.org/queue-data-structure/)** 代表一个 ***先进先出*** 集合的对象。当您需要先进先出访问项目时，可以使用它。当您在列表中添加一个项目时，它被称为**入队**，当您移除一个项目时，它被称为**出队**。**排队<t>。Peek 方法</t>** 用于获取*队列*开头的对象而不将其移除。

**属性:**

*   **入队**在队列末尾添加一个元素。
*   **出列**从队列开始处移除最旧的元素。
*   **Peek** 返回队列开始处最早的元素，但不将其从队列中移除。
*   队列的**容量**是队列可以容纳的元素数量。
*   当元素添加到队列中时，容量会根据需要通过重新分配内部阵列来自动增加。
*   队列接受 **null** 作为引用类型的有效值，并允许重复元素。

**语法:**

```cs
object Peek(); 

```

**返回值:**Peek()方法总是从队列集合中返回第一个项目，而不会将其从队列中移除。在空队列集合上调用 *Peek()* 和*出列()*方法将引发运行时异常 ***“无效操作异常”。***

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to Get object at
// the beginning of the Queue
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
        // contained in the Queue
        Console.Write("Total number of elements in the Queue are : ");

        Console.WriteLine(myQueue.Count);

        // Displaying the beginning element of Queue
        // without removing it from the Queue
        Console.WriteLine("Element at the beginning is : " + myQueue.Peek());

        // Displaying the beginning element of Queue
        // without removing it from the Queue
        Console.WriteLine("Element at the beginning is : " + myQueue.Peek());

        // Displaying the count of elements
        // contained in the Queue
        Console.Write("Total number of elements in the Queue are : ");

        Console.WriteLine(myQueue.Count);
    }
}
```

**Output:**

```cs
Total number of elements in the Queue are : 6
Element at the beginning is : 1st Element
Element at the beginning is : 1st Element
Total number of elements in the Queue are : 6

```

**例 2:**

```cs
// C# code to Get object at
// the beginning of the Queue
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Queue of Integers
        Queue<int> myQueue = new Queue<int>();

        // Displaying the beginning element of Queue
        // without removing it from the Queue
        // Calling Peek() method on empty Queue
        // will throw InvalidOperationException.
        Console.WriteLine("Element at the beginning is : " + myQueue.Peek());
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。无效操作异常:队列为空。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . queue-1 . peek？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.queue-1.peek?view=netframework-4.7.2)