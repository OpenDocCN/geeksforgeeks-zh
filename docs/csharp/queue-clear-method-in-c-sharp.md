# 排队。C# 中的清除方法

> 原文:[https://www . geesforgeks . org/queue-clear-method-in-c-sharp/](https://www.geeksforgeeks.org/queue-clear-method-in-c-sharp/)

此方法用于从队列中移除对象。这个方法是一个 O(n)运算，其中 n 是元素的总数。这个方法属于*系统。集合*命名空间。

**语法:**

```cs
public void Clear ();

```

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to illustrate the
// Queue.Clear Method
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Queue
        Queue q = new Queue();

        // Inserting the elements into the Queue
        q.Enqueue(1);
        q.Enqueue(2);
        q.Enqueue(2);
        q.Enqueue(4);

        // Displaying the count of elements
        // contained in the Queue before
        // removing all the elements
        Console.Write("Total number of elements "+
                           "in the Queue are : ");

        Console.WriteLine(q.Count);

        // Removing all elements from Queue
        q.Clear();

        // Displaying the count of elements
        // contained in the Queue after
        // removing all the elements
        Console.Write("Total number of elements"+
                         " in the Queue are : ");

        Console.WriteLine(q.Count);
    }
}
```

**输出:**

```cs
Total number of elements in the Queue are : 4
Total number of elements in the Queue are : 0

```