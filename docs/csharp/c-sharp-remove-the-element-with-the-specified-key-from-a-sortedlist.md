# C# |从排序列表中删除具有指定键的元素

> 原文:[https://www . geeksforgeeks . org/c-sharp-从排序列表中移除指定键的元素/](https://www.geeksforgeeks.org/c-sharp-remove-the-element-with-the-specified-key-from-a-sortedlist/)

SortedList 类是按键排序的**(键，值)对**的集合。这些对可以通过键和以及索引(从零开始的索引)来访问。这属于**T3 系统。收藏**命名空间。**排序列表。移除(对象)**方法用于从 SortedList 对象中移除具有指定键的元素。

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
public virtual void Remove (object key);

```

这里，*键*是要移除的元素的键。

**异常:**

*   **NotSupportedException :** 如果 SortedList 对象是只读的或者 SortedList 具有固定的大小。
*   **ArgumentNullException :** 如果密钥为空。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to remove the element
// with the specified key from a SortedList
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an SortedList
        SortedList mySortedList = new SortedList();

        // Adding elements to SortedList
        mySortedList.Add("IN", "INDIA");
        mySortedList.Add("NY", "NEW-YORK");
        mySortedList.Add("UK", "UNITED KINGDOM");
        mySortedList.Add("GER", "GERMANY");
        mySortedList.Add("CH", "CHINA");

        // Displaying elements in SortedList
        foreach (string mykey in mySortedList.Keys)
            Console.WriteLine("Key = " + mykey);

        foreach (string myvalue in mySortedList.Values)
            Console.WriteLine("Key = " + myvalue);

        // Removing element having key as "UK"
        Console.WriteLine("Removing element having key as UK");

        mySortedList.Remove("UK");

        // Displaying elements in SortedList
        foreach (string mykey in mySortedList.Keys)
            Console.WriteLine("Key = " + mykey);

        foreach (string myvalue in mySortedList.Values)
            Console.WriteLine("Key = " + myvalue);
    }
}
```

**Output:**

```cs
Key = CH
Key = GER
Key = IN
Key = NY
Key = UK
Key = CHINA
Key = GERMANY
Key = INDIA
Key = NEW-YORK
Key = UNITED KINGDOM
Removing element having key as UK
Key = CH
Key = GER
Key = IN
Key = NY
Key = CHINA
Key = GERMANY
Key = INDIA
Key = NEW-YORK

```

**例 2:**

```cs
// C# code to remove the element
// with the specified key from a SortedList
using System;
using System.Collections;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an SortedList
        SortedList mySortedList = new SortedList();

        // Adding elements to SortedList
        mySortedList.Add("IN", "INDIA");
        mySortedList.Add("NY", "NEW-YORK");
        mySortedList.Add("UK", "UNITED KINGDOM");
        mySortedList.Add("GER", "GERMANY");
        mySortedList.Add("CH", "CHINA");

        // Displaying elements in SortedList
        foreach (string mykey in mySortedList.Keys)
            Console.WriteLine("Key = " + mykey);

        foreach (string myvalue in mySortedList.Values)
            Console.WriteLine("Key = " + myvalue);

        // Removing element having key as null
        Console.WriteLine("Removing element having key as null");

        // It should raise ArgumentNullException
        // as key can not be null
        mySortedList.Remove(null);

        // Displaying elements in SortedList
        foreach (string mykey in mySortedList.Keys)
            Console.WriteLine("Key = " + mykey);

        foreach (string myvalue in mySortedList.Values)
            Console.WriteLine("Key = " + myvalue);
    }
}
```

**错误:**

> 未处理异常:
> 系统。ArgumentNullException:键不能为空。
> 参数名称:键

**注:**

*   如果排序列表对象不包含具有指定键的元素，则排序列表保持不变。不会引发异常。
*   这个方法是一个 O(n)运算，其中 n 是 Count。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . sorted list . remove？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.sortedlist.remove?view=netframework-4.7.2)