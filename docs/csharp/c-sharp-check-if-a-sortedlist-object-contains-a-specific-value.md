# C# |检查排序列表对象是否包含特定值

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-a-sorted list-object-contains-a-specific-value/](https://www.geeksforgeeks.org/c-sharp-check-if-a-sortedlist-object-contains-a-specific-value/)

SortedList 类是按键排序的**(键，值)对**的集合。这些对可以通过键和以及索引(从零开始的索引)来访问。这属于*T3 系统。收藏*命名空间。**排序列表。ContainsValue(Object)** 方法用于检查 SortedList 对象是否包含特定值。

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
public virtual bool ContainsValue (object value);
```

这里，*值*是要在 SortedList 对象中定位的值，可以为空。
**返回值:**如果 SortedList 对象包含指定值的元素，则该方法返回 ***True*** ，否则返回 ***False*** 。
下面的程序说明了 SortedList 的使用。ContainsValue(Object)方法:
**示例 1:**

## c sharp . c sharp . c sharp . c sharp

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

**Output:** 

```cs
False
```