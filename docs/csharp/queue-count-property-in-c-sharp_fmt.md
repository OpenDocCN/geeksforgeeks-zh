# C# 中的 Queue.Count 属性

> 原文：[https://www.geeksforgeeks.org/queue-count-property-in-c-sharp/](https://www.geeksforgeeks.org/queue-count-property-in-c-sharp/)

此属性用于获取队列中包含的元素数量。检索该属性的值是一个 O(1) 操作，它属于 `System.Collections` 命名空间。

## 语法

```cs
public virtual int Count { get; }
```

## 属性值

该属性返回队列中包含的元素数量。

以下程序说明了上述属性的使用：

## 示例 1

```cs
// C# code to illustrate the 
// Queue.Count Property
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Queue
        Queue myQueue = new Queue();

        // Displaying the count of elements
        // contained in the Queue
        Console.Write("Total number of elements"+
                      " in the Queue are : ");

        // The function should return 0
        // as the Queue is empty and it
        // doesn't contain any element
        Console.WriteLine(myQueue.Count);
    }
}
```

**输出：**

```cs
Total number of elements in the Queue are : 0
```

## 示例 2

```cs
// C# code to illustrate the 
// Queue.Count Property
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Queue
        Queue myQueue = new Queue();

        // Inserting the elements into the Queue
        myQueue.Enqueue("C");
        myQueue.Enqueue("C++");
        myQueue.Enqueue("Java");
        myQueue.Enqueue("C#");
        myQueue.Enqueue("HTML");
        myQueue.Enqueue("CSS");

        // Displaying the count of elements
        // contained in the Queue
        Console.Write("Total number of elements "+
                      "in the Queue are : ");

        Console.WriteLine(myQueue.Count);
    }
}
```

**输出：**

```cs
Total number of elements in the Queue are : 6
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.queue.count?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.queue.count?view=netframework-4.7.2)