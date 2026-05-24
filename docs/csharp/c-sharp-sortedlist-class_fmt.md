# C# SortedList 类

> 原文: [https://www.geeksforgeeks.org/c-sharp-sortedlist-class/](https://www.geeksforgeeks.org/c-sharp-sortedlist-class/)

`SortedList` 类是按键排序的 **(键，值)** 对的集合。这些对可以通过键和以及索引(从零开始的索引)来访问。这属于 `System.Collections` 命名空间。

**SortedList 类的特征:**

*   `SortedList` 元素可以通过它的键或索引来访问。
*   `SortedList` 对象在内部维护两个数组来存储列表元素，即一个数组用于键，另一个数组用于关联值。
*   键不能为空，但值可以为空。
*   `SortedList` 对象的容量是 `SortedList` 可以容纳的元素数量。
*   `SortedList` 不允许重复键。
*   由于排序，对 `SortedList` 对象的操作往往比对 `Hashtable` 对象的操作慢。
*   可以使用整数索引访问此集合中的元素。此集合中的索引从零开始。

## 构造器

| 构造器 | 描述 |
| --- | --- |
| `SortedList()` | 初始化 `SortedList` 类的新实例，该实例为空，具有默认的初始容量，并根据添加到 `SortedList` 对象的每个键实现的 `IComparable` 接口进行排序。 |
| `SortedList(IComparer)` | 初始化 `SortedList` 类的新实例，该实例为空，具有默认的初始容量，并根据指定的 `IComparer` 接口进行排序。 |
| `SortedList(IComparer, Int32)` | 初始化 `SortedList` 类的新实例，该实例为空，具有指定的初始容量，并根据指定的 `IComparer` 接口进行排序。 |
| `SortedList(IDictionary)` | 初始化 `SortedList` 类的新实例，该实例包含从指定字典复制的元素，具有与复制的元素数量相同的初始容量，并根据每个键实现的 `IComparable` 接口进行排序。 |
| `SortedList(IDictionary, IComparer)` | 初始化 `SortedList` 类的新实例，该实例包含从指定字典复制的元素，具有与复制的元素数量相同的初始容量，并根据指定的 `IComparer` 接口进行排序。 |
| `SortedList(Int32)` | 初始化 `SortedList` 类的新实例，该实例为空，具有指定的初始容量，并根据添加到 `SortedList` 对象的每个键实现的 `IComparable` 接口进行排序。 |

**示例:**

```cs
// C# Program to create a SortedList
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

**输出:**

```cs
0
```

## 属性

| 属性 | 描述 |
| --- | --- |
| `Capacity` | 获取或设置 `SortedList` 对象的容量。 |
| `Count` | 获取 `SortedList` 对象中包含的元素数量。 |
| `IsFixedSize` | 获取一个值，该值指示 `SortedList` 对象是否具有固定大小。 |
| `IsReadOnly` | 获取一个值，该值指示 `SortedList` 对象是否为只读。 |
| `IsSynchronized` | 获取一个值，该值指示对 `SortedList` 对象的访问是否同步(线程安全)。 |
| `Item[Object]` | 获取和设置与 `SortedList` 对象中的特定键关联的值。 |
| `Keys` | 获取 `SortedList` 对象中的键。 |
| `Values` | 获取 `SortedList` 对象中的值。 |

**示例:**

```cs
// C# Program to illustrate the
// properties of SortedList Class
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating an SortedList
        SortedList mySortedList = new SortedList();

        // Adding elements to SortedList
        mySortedList.Add("1", "one");
        mySortedList.Add("2", "two");
        mySortedList.Add("3", "three");
        mySortedList.Add("4", "four");
        mySortedList.Add("5", "five");

        // Checking if a SortedList
        // object has a fixed size
        Console.WriteLine(mySortedList.IsFixedSize);

        // Checking if the created
        // SortedList is read-only or not
        Console.WriteLine(mySortedList.IsReadOnly);
    }
}
```

**输出:**

```cs
False
False
```

## 方法

| 方法 | 描述 |
| --- | --- |
| `Add(Object, Object)` | 将具有指定键和值的元素添加到 `SortedList` 对象中。 |
| `Clear()` | 从 `SortedList` 对象中移除所有元素。 |
| `Clone()` | 创建 `SortedList` 对象的浅拷贝。 |
| `Contains(Object)` | 确定 `SortedList` 对象是否包含特定的键。 |
| `ContainsKey(Object)` | 确定 `SortedList` 对象是否包含特定的键。 |
| `ContainsValue(Object)` | 确定 `SortedList` 对象是否包含特定值。 |
| `CopyTo(Array, Int32)` | 从数组中的指定索引开始，将 `SortedList` 元素复制到一维数组对象。 |
| `Equals(Object)` | 确定指定的对象是否等于当前对象。 |
| `GetByIndex(Int32)` | 获取 `SortedList` 对象的指定索引处的值。 |
| `GetEnumerator()` | 返回迭代 `SortedList` 对象的 `IDictionaryEnumerator` 对象。 |
| `GetHashCode()` | 用作默认哈希函数。 |
| `GetKey(Int32)` | 获取 `SortedList` 对象的指定索引处的键。 |
| `GetKeyList()` | 获取 `SortedList` 对象中的键。 |
| `GetType()` | 获取当前实例的类型。 |
| `GetValueList()` | 获取 `SortedList` 对象中的值。 |
| `IndexOfKey(Object)` | 返回 `SortedList` 对象中指定键的从零开始的索引。 |
| `IndexOfValue(Object)` | 返回 `SortedList` 对象中指定值的第一个匹配项的从零开始的索引。 |
| `MemberwiseClone()` | 创建当前对象的浅拷贝。 |
| `Remove(Object)` | 从 `SortedList` 对象中移除具有指定键的元素。 |
| `RemoveAt(Int32)` | 移除 `SortedList` 对象的指定索引处的元素。 |
| `SetByIndex(Int32, Object)` | 替换 `SortedList` 对象中特定索引处的值。 |
| `Synchronized(SortedList)` | 返回 `SortedList` 对象的同步(线程安全)包装。 |
| `ToString()` | 返回表示当前对象的字符串。 |
| `TrimToSize()` | 将容量设置为 `SortedList` 对象中元素的实际数量。 |

**例 1:**

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
        Console.WriteLine("Capacity of SortedList is : "
                          + mySortedList.Capacity);

        // Removing all elements from SortedList
        mySortedList.Clear();

        // Displaying number of elements
        Console.WriteLine("Number of elements in SortedList is : "
                          + mySortedList.Count);
    }
}
```

// Displaying capacity
        Console.WriteLine("capacity of SortedList is : "
                          + mySortedList.Capacity);
    }
}
```

### 输出:

```cs
Number of elements in SortedList is : 7
capacity of SortedList is : 16
Number of elements in SortedList is : 0
capacity of SortedList is : 16
```

## 例 2:

```cs
// C# code to check if a SortedList
// object contains a specific value
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

// Checking if a SortedList object
        // contains a specific value
        Console.WriteLine(mySortedList.ContainsValue(null));
    }
}
```

### 输出:

```cs
False
```

### 参考:

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.sortedlist?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.sortedlist?view=netframework-4.7.2)