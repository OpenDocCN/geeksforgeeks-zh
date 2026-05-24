# 排队。C# 中的克隆()方法

> 原文:[https://www . geesforgeks . org/queue-clone-method-in-c-sharp/](https://www.geeksforgeeks.org/queue-clone-method-in-c-sharp/)

此方法用于创建队列的 *[浅拷贝](https://www.geeksforgeeks.org/shallow-copy-and-deep-copy-in-c-sharp/)* 。它只是创建了队列的一个副本。副本将引用内部元素的克隆，但不引用原始元素。

> **语法:**公共虚拟对象 Clone()；
> 
> **返回值:**该方法返回的对象只是队列的浅拷贝。

**示例 1:** 让我们看一个不使用 Clone()方法，而是使用赋值运算符“=”直接复制队列的示例。在下面的代码中，我们可以看到，即使我们将()元素从 myQueue2 中出列，myQueue 的内容也会发生变化。这是因为“=”只是将我的队列的引用分配给了我的队列 2，并没有创建任何新的队列。但是 Clone()会创建一个新的队列。

```cs
// C# program to Copy a Queue using 
// the assignment operator
using System;
using System.Collections;

class GFG {

    // Main Method
    public static void Main(string[] args)
    {

        Queue myQueue = new Queue();
        myQueue.Enqueue("Geeks");
        myQueue.Enqueue("Class");
        myQueue.Enqueue("Noida");
        myQueue.Enqueue("UP");

        // Creating a copy using the 
        // assignment operator.
        Queue myQueue2 = myQueue; 

        myQueue2.Dequeue();

        PrintValues(myQueue);
    }

    public static void PrintValues(IEnumerable myCollection)
    {
        // This method prints all the
        // elements in the Stack.
        foreach(Object obj in myCollection)
            Console.WriteLine(obj);
    }
}
```

**输出:**

```cs
Class
Noida
UP

```