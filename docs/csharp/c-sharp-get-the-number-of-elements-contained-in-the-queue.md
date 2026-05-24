# C# |获取队列中包含的元素数量

> 原文:[https://www . geeksforgeeks . org/c-sharp-获取队列中包含的元素数量/](https://www.geeksforgeeks.org/c-sharp-get-the-number-of-elements-contained-in-the-queue/)

[队列](https://www.geeksforgeeks.org/queue-data-structure/)代表一个 ***先进先出*** 集合的对象。当您需要先进先出访问项目时，可以使用它。当您在列表中添加一个项目时，它被称为**入队**，当您移除一个项目时，它被称为**出队**。**排队<t>。计数属性</t>** 用于获取队列中包含的元素数量。

**属性:**

*   **入队**在队列末尾添加一个元素。
*   **出列**从队列开始处移除最旧的元素。
*   **Peek** 返回队列开始处最早的元素，但不将其从队列中移除。
*   队列的**容量**是队列可以容纳的元素数量。
*   当元素添加到队列中时，容量会根据需要通过重新分配内部阵列来自动增加。
*   队列接受 **null** 作为引用类型的有效值，并允许重复元素。

**语法:**

```cs
myQueue.Count 

```

这里，*我的队列*是队列的名称。

**返回值:**该属性返回队列中包含的元素数量。

**例 1:**

```cs
// C# code to Get the number of
// elements contained in the Queue
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Queue of strings
        Queue<string> myQueue = new Queue<string>();

        // Inserting the elements into the Queue
        myQueue.Enqueue("Chandigarh");
        myQueue.Enqueue("Delhi");
        myQueue.Enqueue("Noida");
        myQueue.Enqueue("Himachal");
        myQueue.Enqueue("Punjab");
        myQueue.Enqueue("Jammu");

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

```

**例 2:**

```cs
// C# code to Get the number of
// elements contained in the Queue
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Queue of Integers
        Queue<int> myQueue = new Queue<int>();

        // Displaying the count of elements
        // contained in the Queue
        Console.Write("Total number of elements in the Queue are : ");

        // The function should return 0
        // as the Queue is empty and it
        // doesn't contain any element
        Console.WriteLine(myQueue.Count);
    }
}
```

**Output:**

```cs
Total number of elements in the Queue are : 0

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . queue-1 . count？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.queue-1.count?view=netframework-4.7.2)