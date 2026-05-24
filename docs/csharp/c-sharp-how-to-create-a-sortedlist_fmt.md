# C# 中如何创建 SortedList

> 原文：[https://www.geeksforgeeks.org/c-sharp-how-to-create-a-sortedlist/](https://www.geeksforgeeks.org/c-sharp-how-to-create-a-sortedlist/)

`SortedList` 类是按键排序的 `(key, value)` 对的集合。这些对可以通过键以及索引（从零开始的索引）来访问。这属于 `System.Collections` 命名空间。

## SortedList 的属性

*   在内部，`SortedList` 的对象维护两个数组。第一个数组用于存储列表中的元素，即键，第二个数组用于存储相关的值。
*   键不能为空，但值可以为空。
*   由于 `SortedList` 使用了排序，这使得它比 `Hashtable` 慢。
*   `SortedList` 的容量可以通过重新分配来动态增加。
*   `SortedList` 中的键不能重复，但值可以重复。
*   `SortedList` 可以使用 `IComparer`（升序或降序）根据关键字进行排序。

下面的程序说明了如何创建排序列表：

## 示例 1

```cs
// C# Program to illustrate how
// to create a SortedList
using System;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {
        // Creating object of SortedList
        // fslist is the SortedList object
        SortedList fslist = new SortedList();

        // Count property is used to get the
        // number of key/value pairs in fslist
        // It will give 0 as no pairs are present
        Console.WriteLine(fslist.Count);
    }
}
```

**输出：**

```cs

```

## 示例 2

```cs
// C# Program to illustrate how
// to create a SortedList
using System;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {
        // Creating object of SortedList
        // fslist is the SortedList object
        SortedList fslist = new SortedList();

        // Count property is used to get the
        // number of key/value pairs in fslist
        // It will give 0 as no pairs are present
        Console.WriteLine(fslist.Count);

        // Adding key/value pairs in fslist
        fslist.Add("1", "GFG");
        fslist.Add("2", "Geeks");
        fslist.Add("3", "for");
        fslist.Add("4", "Geeks");

        // Count property is used to get the
        // number of key/value pairs in fslist
        // It will give output 4
        Console.WriteLine(fslist.Count);
    }
}
```

**输出：**

```cs

```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.sortedlist?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.sortedlist?view=netframework-4.7.2)