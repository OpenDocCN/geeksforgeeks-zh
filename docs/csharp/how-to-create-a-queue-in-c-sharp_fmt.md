# 如何在 C# 中创建队列

> 原文：[https://www.geeksforgeeks.org/how-to-create-a-queue-in-c-sharp/](https://www.geeksforgeeks.org/how-to-create-a-queue-in-c-sharp/)

`Queue()`构造函数用于初始化 `Queue` 类的一个新实例，该实例将为空，并将具有默认的初始容量，并使用默认的增长因子。队列表示对象的先进先出集合。当您需要先进先出访问项目时，可以使用它。当您在列表中添加一个项目时，它被称为入队，当您移除一个项目时，它被称为出列。这个类属于 `System.Collections` 命名空间并实现 `ICollection`、`IEnumerable` 和 `ICloneable` 接口。

## 语法：

```cs
public Queue ();
```

## 重要提示：

*   队列的 `capacity` 表示队列可以容纳的元素数量。随着元素增加，它会通过重新分配自动增大。
*   `TrimToSize` 方法用于减少队列容量。
*   当需要更多容量时，当前容量会乘以一个称为 `growth factor` 的数。
*   此构造函数是一个 O(1) 操作。

## 例 1：

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

## 输出：

```cs

```