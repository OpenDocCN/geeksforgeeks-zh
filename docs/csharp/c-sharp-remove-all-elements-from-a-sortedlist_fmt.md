# C# | 从排序列表中移除所有元素

> 原文：[https://www.geeksforgeeks.org/c-sharp-remove-all-elements-from-a-sortedlist/](https://www.geeksforgeeks.org/c-sharp-remove-all-elements-from-a-sortedlist/)

`SortedList` 类是按键排序的 **(键，值) 对** 的集合。这些对可以通过键以及索引（从零开始的索引）来访问。这属于 `System.Collections` 命名空间。`SortedList.Clear()` 方法用于从 `SortedList` 对象中移除所有元素。

## 属性

*   `SortedList` 元素可以通过它的键或索引来访问。
*   `SortedList` 对象在内部维护两个数组来存储列表元素，即一个数组用于键，另一个数组用于关联值。
*   键不能为空，但值可以为空。
*   `SortedList` 对象的 `Capacity` 是 `SortedList` 可以容纳的元素数量。
*   `SortedList` 不允许重复键。
*   由于排序，对 `SortedList` 对象的操作往往比对 `Hashtable` 对象的操作慢。
*   可以使用整数索引访问此集合中的元素。此集合中的索引从零开始。

## 语法

```cs
public virtual void Clear();
```

## 异常

*   `NotSupportedException`：如果 `SortedList` 对象是只读的或具有固定大小。

## 示例

```cs
// C# code to remove all
// elements from a SortedList
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an SortedList
        SortedList mySortedList = new SortedList();

        // Adding elements to SortedList
        mySortedList.Add("1", "1st");
        mySortedList.Add("2", "2nd");
        mySortedList.Add("3", "3rd");
        mySortedList.Add("4", "4th");
        mySortedList.Add("5", "5th");
        mySortedList.Add("6", "6th");
        mySortedList.Add("7", "7th");

        // Displaying number of elements
        Console.WriteLine("Number of elements in SortedList is : "
                         + mySortedList.Count);

        // Displaying capacity
        Console.WriteLine("capacity of SortedList is : "
                         + mySortedList.Capacity);

        // Removing all elements from SortedList
        mySortedList.Clear();

        // Displaying number of elements
        Console.WriteLine("Number of elements in SortedList is : "
                         + mySortedList.Count);

        // Displaying capacity
        Console.WriteLine("capacity of SortedList is : "
                         + mySortedList.Capacity);
    }
}
```

## 输出

```cs
Number of elements in SortedList is : 7
capacity of SortedList is : 16
Number of elements in SortedList is : 0
capacity of SortedList is : 16
```

## 注

*   这个方法是一个 O(n) 运算，其中 n 是 `Count`。
*   `Count` 被设置为零，并且集合元素对其他对象的引用也被释放。
*   容量保持不变。要重置 `SortedList` 对象的容量，请调用 `TrimToSize` 或直接设置 `Capacity` 属性。
*   修剪空 `SortedList` 将 `SortedList` 的容量设置为默认容量。

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.sortedlist.clear?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.sortedlist.clear?view=netframework-4.7.2)