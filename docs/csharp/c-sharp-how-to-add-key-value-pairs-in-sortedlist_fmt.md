# C# 如何在 SortedList 中添加键/值对

> 原文: [https://www.geeksforgeeks.org/c-sharp-how-to-add-key-value-pairs-in-sortedlist/](https://www.geeksforgeeks.org/c-sharp-how-to-add-key-value-pairs-in-sortedlist/)

`SortedList` 类是按键排序的 **(键, 值) 对**的集合。这些对可以通过键以及索引（从零开始的索引）来访问。这属于 `System.Collections` 命名空间。`SortedList.Add(Object, Object)` 方法用于向 `SortedList` 对象添加具有指定键和值的元素。

## SortedList 的属性

*   在内部，`SortedList` 的对象维护两个数组。第一个数组用于存储列表中的元素，即键，第二个数组用于存储相关的值。
*   键不能为空，但值可以为空。
*   由于 `SortedList` 使用了排序，这使得它比 `Hashtable` 慢。
*   `SortedList` 的容量可以通过重新分配来动态增加。
*   `SortedList` 中的键不能重复，但值可以重复。
*   `SortedList` 可以使用 `IComparer`（升序或降序）根据关键字进行排序。

## 语法

```cs
public virtual void Add (object key, object value);
```

## 参数

> **key**: 是要添加的元素的键。
>
> **value**: 是待加元素的值。该值可以为空。

## 异常

*   `ArgumentNullException`: 如果键为空。
*   `ArgumentException`: 如果具有指定键的元素已经存在于 `SortedList` 对象中，或者 `SortedList` 被设置为使用 `IComparable` 接口，并且该键没有实现 `IComparable` 接口。
*   `NotSupportedException`: 如果 `SortedList` 是只读的或具有固定大小。
*   `OutOfMemoryException`: 如果系统中没有足够的可用内存将这些对添加到 `SortedList` 中。
*   `InvalidOperationException`: 如果比较器抛出异常。

以下程序说明了上述方法的使用:

### 例 1

```cs
// C# program to illustrate how to add key/value
// pair in SortedList
using System;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {
        // Creating a sorted list of key/value pairs
        SortedList fslist = new SortedList();

        // Adding pairs to fslist
        fslist.Add("Maths    ", 98);
        fslist.Add("English  ", 99);
        fslist.Add("Physics  ", 97);
        fslist.Add("Chemistry", 96);
        fslist.Add("CSE      ", 100);

        // Displays the marks in different
        // subjects sorted according to keys
        // i.e subjects
        // Here Count property is used to count
        // the total number of pairs in SortedList
        for (int i = 0; i < fslist.Count; i++) {
            Console.WriteLine("{0}:\t{1}", fslist.GetKey(i),
                                      fslist.GetByIndex(i));
        }
    }
}
```

**输出:**

```cs
Chemistry:    96
CSE      :    100
English  :    99
Maths    :    98
Physics  :    97
```

### 例 2

```cs
// C# program to illustrate how to add
// key/value pair in SortedList
using System;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {
        // Creating a sorted list of key/value pairs
        SortedList fslist = new SortedList();

        // Adding pairs to fslist
        fslist.Add("Maths    ", 98);
        fslist.Add("English  ", 99);
        fslist.Add("Physics  ", 97);
        fslist.Add("Chemistry", 96);

        // this will give error as we are
        // adding duplicate key i.e Chemistry
        fslist.Add("Chemistry", 100);
    }
}
```

**错误:**

> 未处理异常:
> System.ArgumentException: 项目已添加。字典中的键:“Chemistry” 正在添加:“Chemistry”
>    在 System.Collections.SortedList.Add(Object key, Object value)
>    在 Geeks.Main(String[] args)

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.sortedlist.add?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.sortedlist.add?view=netframework-4.7.2)