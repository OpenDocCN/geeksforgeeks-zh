# C# |在排序列表对象中搜索

> 原文:[https://www . geesforgeks . org/c-sharp-search-in-a-sorted list-object/](https://www.geeksforgeeks.org/c-sharp-search-in-a-sortedlist-object/)

SortedList 类是按键排序的**(键，值)对**的集合。这些对可以通过键和以及索引(从零开始的索引)来访问。这属于**T3 系统。收藏**命名空间。**排序列表。ContainsKey(Object)** 方法用于检查 SortedList 对象是否包含特定的键。

**属性:**

*   SortedList 元素可以通过它的键或索引来访问。
*   SortedList 对象在内部维护两个数组来存储列表元素，即一个数组用于键，另一个数组用于关联值。
*   键不能为空，但值可以为空。
*   排序列表对象的**容量**是排序列表可以容纳的元素数量。
*   排序列表不允许重复键。
*   由于排序，对 SortedList 对象的操作往往比对 Hashtable 对象的操作慢。
*   可以使用整数索引访问此集合中的元素。此集合中的索引从零开始。

**语法:**

```cs
public virtual bool ContainsKey (object key);

```

这里，*键*是在 SortedList 对象中定位的键。

**返回值:**如果 SortedList 对象包含具有指定键的元素，该方法将返回 *True* ，否则返回 *False* 。

**异常:**

*   **ArgumentNullException :** 如果密钥为空。
*   **无效操作异常:**如果比较器抛出异常。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to check if a SortedList
// object contains a specific key
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an SortedList
        SortedList mySortedList = new SortedList();

        // Adding elements to SortedList
        mySortedList.Add("h", "Hello");
        mySortedList.Add("g", "Geeks");
        mySortedList.Add("f", "For");
        mySortedList.Add("n", "Noida");

        // Checking if a SortedList object
        // contains a specific key
        Console.WriteLine(mySortedList.ContainsKey("g"));
    }
}
```

**Output:**

```cs
True

```

**例 2:**

```cs
// C# code to check if a SortedList
// object contains a specific key
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an SortedList
        SortedList mySortedList = new SortedList();

        // Adding elements to SortedList
        mySortedList.Add("h", "Hello");
        mySortedList.Add("g", "Geeks");
        mySortedList.Add("f", "For");
        mySortedList.Add("n", "Noida");

        // Checking if a SortedList object
        // contains a specific key
        // It should throw ArgumentNullException
        // as the Key can not be null
        Console.WriteLine(mySortedList.ContainsKey(null));
    }
}
```

**错误:**

> 未处理异常:
> 系统。ArgumentNullException:键不能为空。
> 参数名称:键

**注:**该方法采用二分搜索法算法，因此，该方法为 O(log n)运算，其中 n 为 Count。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . sorted list . contains key？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.sortedlist.containskey?view=netframework-4.7.2)