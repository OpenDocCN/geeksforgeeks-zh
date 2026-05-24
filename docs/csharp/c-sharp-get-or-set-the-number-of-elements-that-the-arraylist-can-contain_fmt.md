# C# | 获取或设置数组列表可以包含的元素数量

> 原文：[https://www.geeksforgeeks.org/c-sharp-get-or-set-the-number-of-elements-that-the-arraylist-can-contain/](https://www.geeksforgeeks.org/c-sharp-get-or-set-the-number-of-elements-that-the-arraylist-can-contain/)

`ArrayList`表示可以单独索引的对象的有序集合。它基本上是数组的替代。它还允许动态内存分配、添加、搜索和排序列表中的项目。`ArrayList.Capacity`属性用于获取或设置数组列表可以包含的元素数量。

## 数组列表类的属性

*   可以在任何时间点向数组列表集合中添加或移除元素。
*   数组不保证排序。
*   数组的容量是数组列表可以容纳的元素数量。
*   可以使用整数索引访问此集合中的元素。此集合中的索引是从零开始的。
*   也允许重复元素。
*   多维数组不作为数组列表集合中的元素受支持。

## 语法

```cs
public virtual int Capacity { get; set; }
```

**返回值：** 数组列表可以包含的元素数量。

## 异常

*   `ArgumentOutOfRangeException`：如果容量设置为小于`Count`的值，即数组列表中的元素数量。
*   `OutOfMemoryException`：如果系统上没有足够的可用内存。

## 例

```cs
// C# code to get or set the number 
// of elements that the ArrayList can contain
using System; 
using System.Collections;

class GFG {

    // Driver code
    public static void Main() {

        // Creating an ArrayList
        ArrayList myList = new ArrayList();

        // Adding elements to ArrayList
        myList.Add(1);
        myList.Add(2);
        myList.Add(3);
        myList.Add(4);
        myList.Add(5);

        // Displaying count of elements of ArrayList
        Console.WriteLine("Number of elements: " + myList.Count);

        // Displaying Current capacity of ArrayList
        Console.WriteLine("Current capacity: " + myList.Capacity); 
    } 
}
```

## 输出

```cs
Number of elements: 5
Current capacity: 8
```

## 要点

*   `Capacity`是数组列表可以存储的元素数量。`Count`是数组列表中实际的元素数量。
*   容量总是大于或等于`Count`。如果在添加元素时`Count`超过了容量，系统会在复制旧元素和添加新元素之前，通过重新分配内部数组来自动增加容量。

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.capacity?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.capacity?view=netframework-4.7.2)