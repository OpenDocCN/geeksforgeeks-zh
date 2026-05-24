# C# |将队列转换为数组

> 原文:[https://www . geesforgeks . org/c-sharp-convert-queue-to-array/](https://www.geeksforgeeks.org/c-sharp-convert-queue-to-array/)

**[队列](https://www.geeksforgeeks.org/queue-data-structure/)** 代表一个 ***先进先出*** 集合的对象。当您需要先进先出访问项目时，可以使用它。当您在列表中添加一个项目时，它被称为**入队**，当您移除一个项目时，它被称为**出队**。**排队<t>。ToArray 方法</t>** 用于将*队列*元素复制到新数组中。

**属性:**

*   **入队**在队列末尾添加一个元素。
*   **出列**从队列开始处移除最旧的元素。
*   **Peek** 返回队列开始处最早的元素，但不将其从队列中移除。
*   队列的**容量**是队列可以容纳的元素数量。
*   当元素添加到队列中时，容量会根据需要通过重新分配内部阵列来自动增加。
*   队列接受 **null** 作为引用类型的有效值，并允许重复元素。

**语法:**

```cs
public virtual object[] ToArray();

```

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to Convert Queue to array
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

        // Converting the Queue into array
        String[] arr = myQueue.ToArray();

        // Displaying the elements in array
        foreach(string str in arr)
        {
            Console.WriteLine(str);
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
// C# code to Convert Queue to array
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Queue of Integers
        Queue<int> myQueue = new Queue<int>();

        // Inserting the elements into the Queue
        myQueue.Enqueue(2);
        myQueue.Enqueue(3);
        myQueue.Enqueue(4);
        myQueue.Enqueue(5);
        myQueue.Enqueue(6);

        // Converting the Queue into array
        int[] arr = myQueue.ToArray();

        // Displaying the elements in array
        foreach(int i in arr)
        {
            Console.WriteLine(i);
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

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . queue-1 . to array？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.queue-1.toarray?view=netframework-4.7.2)