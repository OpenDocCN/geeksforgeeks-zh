# 排队。C# 中的数组方法

> 原文:[https://www . geesforgeks . org/queue-to array-method-in-c-sharp/](https://www.geeksforgeeks.org/queue-toarray-method-in-c-sharp/)

此方法用于将队列元素复制到新数组中。队列不会被修改，新数组中元素的顺序与从队列开始到结束的元素顺序相同。这个方法是一个操作，属于

**语法:**

```cs
public virtual object[] ToArray ();
```

**返回值:**返回一个包含从队列中复制的元素的新数组。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to illustrate the 
// Queue.ToArray Method 
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Queue
        Queue myQueue = new Queue();

        // Inserting the elements into the Queue
        myQueue.Enqueue("Geeks");
        myQueue.Enqueue("Geeks Classes");
        myQueue.Enqueue("Noida");
        myQueue.Enqueue("Data Structures");
        myQueue.Enqueue("GeeksforGeeks");

        // Converting the Queue into array
        Object[] arr = myQueue.ToArray();

        // Displaying the elements in array
        foreach(Object ob in arr)
        {
            Console.WriteLine(ob);
        }
    }
}
```

**Output:**

```cs
Geeks
Geeks Classes
Noida
Data Structures
GeeksforGeeks

```

**例 2:**

```cs
// C# code to illustrate the 
// Queue.ToArray Method 
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Queue
        Queue myQueue = new Queue();

        // Inserting the elements into the Queue
        myQueue.Enqueue(2);
        myQueue.Enqueue(3);
        myQueue.Enqueue(4);
        myQueue.Enqueue(5);
        myQueue.Enqueue(6);

        // Converting the Queue into array
        Object[] arr = myQueue.ToArray();

        // Displaying the elements in array
        foreach(Object ob in arr)
        {
            Console.WriteLine(ob);
        }
    }
}
```

**Output:**

```cs
2
3
4
5
6

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . queue . to array？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.queue.toarray?view=netframework-4.7.2)