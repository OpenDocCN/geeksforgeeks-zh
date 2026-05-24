# C# |队列<t>。带示例的三进制方法</t>T3

> 原文:[https://www . geeksforgeeks . org/c-sharp-queue-trimexcess-method-with-examples/](https://www.geeksforgeeks.org/c-sharp-queue-trimexcess-method-with-examples/)

**[队列](https://www.geeksforgeeks.org/queue-data-structure/)** 代表先进先出的集合对象。当您需要先进先出访问项目时，可以使用它。当您在列表中添加一个项目时，它被称为入队，当您删除一个项目时，它被称为出列。
**排队< T >。TrimExcess 方法**用于将容量设置为队列中元素的实际数量< **T** >，如果该数量小于当前容量的 90%。

队列是一种无界的数据结构，在 C# 中没有计算队列容量的方法。它是动态的，取决于系统内存。这种方法通常用于大型队列的内存管理。
**队列属性:**

*   排队将一个元素添加到队列的末尾。
*   出列从队列的开头移除最旧的元素。
*   Peek 返回队列开头最早的元素，但不会将其从队列中移除。
*   队列的容量是队列可以容纳的元素数量。
*   当元素添加到队列中时，容量会根据需要通过重新分配内部阵列来自动增加。
*   队列接受 null 作为引用类型的有效值，并允许重复元素。

**语法:**

```cs
public void TrimExcess ();

```

**注:**

*   如果没有新元素添加到集合中，此方法可用于最小化集合的内存开销。
*   要将队列< **T** >重置为初始状态，请在调用 TrimExcess 方法之前调用[清除](https://www.geeksforgeeks.org/c-remove-all-objects-from-the-queue/)方法。
*   修剪空队列< **T** >将队列< **T** >的容量设置为默认容量。

下面是一个更好地理解实现的例子:

**示例:**

```cs
// C# code to set the capacity to the
// actual number of elements in the Queue
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Queue of strings
        Queue<string> myQueue = new Queue<string>();

        // Inserting elements into Queue
        myQueue.Enqueue("1st");
        myQueue.Enqueue("2nd");
        myQueue.Enqueue("3rd");
        myQueue.Enqueue("4th");
        myQueue.Enqueue("5th");

        // To display number of elements in Queue
        Console.WriteLine(myQueue.Count);

        // Removing all the elements from Queue
        myQueue.Clear();

        // using TrimExcess method
        myQueue.TrimExcess();

        // To display number of elements in Queue
        Console.WriteLine(myQueue.Count);
    }
}
```

**Output:**

```cs
5
0

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . queue-1 . tri excess？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.queue-1.trimexcess?view=netframework-4.7.2)