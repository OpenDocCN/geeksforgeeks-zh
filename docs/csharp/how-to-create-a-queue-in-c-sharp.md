# 如何在 C# 中创建队列

> 原文:[https://www . geeksforgeeks . org/如何创建 c-sharp 中的队列/](https://www.geeksforgeeks.org/how-to-create-a-queue-in-c-sharp/)

**Queue()构造函数**用于初始化 Queue 类的一个新实例，该实例将为空，并将具有默认的初始容量，并使用默认的增长因子。队列表示对象的先进先出集合。当您需要先进先出访问项目时，可以使用它。当您在列表中添加一个项目时，它被称为入队，当您移除一个项目时，它被称为出列。这个班属于*系统。集合*命名空间并实现 ICollection、IEnumerable 和 ICloneable 接口。

**语法:**

```cs
public Queue ();
```

**重要提示:**

*   The ***capacity*** of the queue represents the number of elements that the queue can accommodate. As the element increases, it will automatically increase through redistribution.
*   ***Trimtosize*** method is used to reduce the queue capacity.
*   When more capacity is needed, the current capacity is multiplied by a number called ***growth factor*** .
*   This constructor is an O(1) operation.

**例 1:**

```cs
// C# Program to illustrate how
// to create a Queue
using System;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // qt is the Queue object
        // Queue() is the constructor
        // used to initializes a new 
        // instance of the Queue class
        Queue qt = new Queue();

        // Count property is used to get the
        // number of elements in Queue
        // It will give 0 as no elements 
        // are present currently
        Console.WriteLine(qt.Count);
    }
}
```

**输出:**

```cs
0

```