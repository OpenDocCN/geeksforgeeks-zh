# C# | 列表容量

> 原文: [https://www.geeksforgeeks.org/c-sharp-capacity-of-a-list/](https://www.geeksforgeeks.org/c-sharp-capacity-of-a-list/)

## `List<T>.Capacity` 属性

`List<T>.Capacity` 属性用于获取或设置内部数据结构在不调整大小的情况下可以容纳的元素总数。

## `List` 属性

*   它不同于数组。列表可以动态调整大小，但数组不能。
*   `List` 类可以接受 `null` 作为引用类型的有效值，并且它还允许重复的元素。
*   如果 `Count` 等于 `Capacity`，则列表的容量会通过重新分配内部数组而自动增加。在添加新元素之前，现有元素将被复制到新数组中。

## 容量 (Capacity) 与 计数 (Count)

*   `Count` 总是小于 `Capacity`。添加元素时，如果 `Count` 超过 `Capacity`，则容量将通过在复制旧元素和添加新元素之前重新分配内部数组来自动增加。
*   `Capacity` 是列表在根据需要调整大小之前可以存储的元素数量。但是 `Count` 是列表中实际存在的元素的数量。
*   如果 `Capacity` 比 `Count` 大得多，用户可以通过调用 `TrimExcess` 方法或将容量显式设置为较低的值来减少容量。
*   如果 `Capacity` 已明确确定，则内部数组也将重新分配以容纳指定的容量，并且所有元素都将被复制。
*   检索 `Capacity` 属性的值是一个 O(1) 操作，而设置 `Capacity` 是一个 O(n) 操作，其中 `n` 是新容量。

## 语法

```cs
public int Capacity { get; set; }
```

## 返回值

该方法返回 `List<T>` 在类型 `T` 的数组需要调整大小之前可以包含的元素数量。返回值类型为 `Int32`。

## 异常

*   `ArgumentOutOfRangeException`: 如果容量设置为小于 `Count` 的值。
*   `OutOfMemoryException`: 如果系统上没有足够的可用内存。

## 示例

以下程序说明了 `Capacity` 属性的使用:

### 例 1

```cs
// C# program to illustrate the
// Capacity Property of List<T>
using System;
using System.Collections.Generic;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {
        // Creating a List of integers
        // Here we are not setting
        // Capacity explicitly
        List<int> firstlist = new List<int>();

        // adding elements in firstlist
        firstlist.Add(1);
        firstlist.Add(2);
        firstlist.Add(3);
        firstlist.Add(4);

        // Printing the Capacity of firstlist
        Console.WriteLine("Capacity Is: " + firstlist.Capacity);

        // Printing the Count of firstlist
        Console.WriteLine("Count Is: " + firstlist.Count);

        // Adding some more
        // elements in firstlist
        firstlist.Add(5);
        firstlist.Add(6);

        // Printing the Capacity of firstlist
        // It will give output 8 as internally
        // List is resized
        Console.WriteLine("Capacity Is: " + firstlist.Capacity);

        // Printing the Count of firstlist
        Console.WriteLine("Count Is: " + firstlist.Count);
    }
}
```

**输出:**

```cs
Capacity Is: 4
Count Is: 4
Capacity Is: 8
Count Is: 6
```

### 例 2

```cs
// C# program to illustrate the
// Capacity Property of List<T>
using System;
using System.Collections.Generic;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {
        // Creating a List of integers
        // Here we are setting Capacity
        // explicitly i.e.
        List<int> firstlist = new List<int>(10);

        // Printing the Capacity of firstlist
        Console.WriteLine("Capacity Is: " + firstlist.Capacity);

        // Printing the Count of firstlist
        Console.WriteLine("Count Is: " + firstlist.Count);

        // adding elements in firstlist
        firstlist.Add(1);
        firstlist.Add(2);
        firstlist.Add(3);
        firstlist.Add(4);

        // Printing the Capacity of firstlist
        Console.WriteLine("Capacity Is: " + firstlist.Capacity);

        // Printing the Count of firstlist
        Console.WriteLine("Count Is: " + firstlist.Count);

        // Adding some more
        // elements in firstlist
        firstlist.Add(5);
        firstlist.Add(6);

        // Printing the Capacity of firstlist
        // It will give output 10 as we have
        // already set the Capacity
        Console.WriteLine("Capacity Is: " + firstlist.Capacity);

        // Printing the Count of firstlist
        Console.WriteLine("Count Is: " + firstlist.Count);
    }
}
```

**输出:**

```cs
Capacity Is: 10
Count Is: 0
Capacity Is: 10
Count Is: 4
Capacity Is: 10
Count Is: 6
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.capacity?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.capacity?view=netframework-4.7.2)