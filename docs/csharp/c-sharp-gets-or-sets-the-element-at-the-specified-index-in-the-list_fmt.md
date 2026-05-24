# C#
## 获取或设置列表中指定索引处的元素

> 原文：[https://www.geeksforgeeks.org/c-sharp-gets-or-sets-the-element-at-the-specified-index-in-the-list/](https://www.geeksforgeeks.org/c-sharp-gets-or-sets-the-element-at-the-specified-index-in-the-list/)

`List<T>.Item[Int32]`属性用于获取或设置指定索引处的元素。

**`List`属性：**

*   它不同于数组。列表可以动态调整大小，但数组不能。
*   `List`类可以接受`null`作为引用类型的有效值，并且它还允许重复的元素。
*   如果`Count`等于`Capacity`，则列表的容量会通过重新分配内部数组而自动增加。在添加新元素之前，现有元素将被复制到新数组中。

**语法：**

```cs
public T this[int index] { get; set; }
```

**参数：**

> **`index`**：是要获取或设置类型为`System.Int32`的元素的从零开始的索引。

**返回值：** 该属性返回指定索引处的元素。

**异常：** 如果`index`小于 0 或`index`等于或大于`[Count](https://www.geeksforgeeks.org/c-count-the-total-number-of-elements-in-the-list/)`，此方法将给出`ArgumentOutOfRangeException`。

下面举例说明`List<T>.Item[Int32]`属性的使用：

**例 1：**

```cs
// C# program to illustrate the
// List.Item[32] property
using System;
using System.Collections.Generic;

class Geeks {

// Main Method
    public static void Main(String[] args)
    {

// Creating a List of Strings
        List<String> firstlist = new List<String>();

// adding elements in firstlist
        firstlist.Add("A");
        firstlist.Add("B");
        firstlist.Add("C");
        firstlist.Add("D");
        firstlist.Add("E");
        firstlist.Add("F");

// getting the element of
        // firstlist using Item property
        Console.WriteLine("Element at index 2: " + firstlist[2]);
    }
}
```

**输出：**

```cs
Element at index 2: C
```

**例 2：**

```cs
// C# program to illustrate the
// List.Item[32] property
using System;
using System.Collections.Generic;

class Geeks {

// Main Method
    public static void Main(String[] args)
    {

// Creating a List of String
        List<String> firstlist = new List<String>();

// adding elements in firstlist
        firstlist.Add("A");
        firstlist.Add("B");
        firstlist.Add("C");
        firstlist.Add("D");
        firstlist.Add("E");
        firstlist.Add("F");

// Before setting the another
        // value of index 2 we will get
        // the element of firstlist
        // using Item property
        Console.WriteLine("Element at index 2: " + firstlist[2]);

// setting the value of Element
        firstlist[2] = "Z";

// displaying the updated value
        Console.WriteLine("After Setting the new value at 2: " + firstlist[2]);
    }
}
```

**输出：**

```cs
Element at index 2: C
After Setting the new value at 2: Z
```

**参考：**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.item?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.item?view=netframework-4.7.2)