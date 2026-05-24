# C# |从排序列表的指定索引中删除

> 原文:[https://www . geeksforgeeks . org/c-sharp-从指定的排序索引列表中删除/](https://www.geeksforgeeks.org/c-sharp-remove-from-the-specified-index-of-a-sortedlist/)

SortedList 类是按键排序的**(键，值)对**的集合。这些对可以通过键和以及索引(从零开始的索引)来访问。这属于**T3 系统。收藏**命名空间。**排序列表。RemoveAt(Int32)** 方法用于移除 SortedList 对象的指定索引处的元素。

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
public virtual void RemoveAt (int index);

```

这里，*索引*是要移除的元素的从零开始的索引。

**异常:**

*   **NotSupportedException :** 如果 SortedList 对象是只读的或者 SortedList 具有固定的大小。
*   **ArgumentOutOfRangeException:**如果索引在 SortedList 对象的有效索引范围之外。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to remove the element at
// the specified index of a SortedList
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an SortedList
        SortedList mySortedList = new SortedList();

        // Adding elements to SortedList
        mySortedList.Add("DS", "Data Structures");
        mySortedList.Add("EE", "Electrical Engineering");
        mySortedList.Add("CS", "Computer Science");
        mySortedList.Add("ME", "Mechanical Engineering");
        mySortedList.Add("CE", "Civil Engineering");

        // Displaying elements in SortedList
        foreach(string mykey in mySortedList.Keys)
            Console.WriteLine("Key = " + mykey);

        foreach(string myvalue in mySortedList.Values)
            Console.WriteLine("Key = " + myvalue);

        // Removing element at index 4
        Console.WriteLine("Removing element at index 4");

        mySortedList.RemoveAt(4);

        // Displaying elements in SortedList
        foreach(string mykey in mySortedList.Keys)
            Console.WriteLine("Key = " + mykey);

        foreach(string myvalue in mySortedList.Values)
            Console.WriteLine("Key = " + myvalue);
    }
}
```

**Output:**

```cs
Key = CE
Key = CS
Key = DS
Key = EE
Key = ME
Key = Civil Engineering
Key = Computer Science
Key = Data Structures
Key = Electrical Engineering
Key = Mechanical Engineering
Removing element at index 4
Key = CE
Key = CS
Key = DS
Key = EE
Key = Civil Engineering
Key = Computer Science
Key = Data Structures
Key = Electrical Engineering

```

**例 2:**

```cs
// C# code to remove the element at
// the specified index of a SortedList
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an SortedList
        SortedList mySortedList = new SortedList();

        // Adding elements to SortedList
        mySortedList.Add("DS", "Data Structures");
        mySortedList.Add("EE", "Electrical Engineering");
        mySortedList.Add("CS", "Computer Science");
        mySortedList.Add("ME", "Mechanical Engineering");
        mySortedList.Add("CE", "Civil Engineering");

        // Displaying elements in SortedList
        foreach(string mykey in mySortedList.Keys)
            Console.WriteLine("Key = " + mykey);

        foreach(string myvalue in mySortedList.Values)
            Console.WriteLine("Key = " + myvalue);

        // Removing element at index 8
        Console.WriteLine("Removing element at index 8");

        // It should raise ArgumentOutOfRangeException
        // As index is outside the range of valid
        // indexes for the SortedList object.
        mySortedList.RemoveAt(8);

        // Displaying elements in SortedList
        foreach(string mykey in mySortedList.Keys)
            Console.WriteLine("Key = " + mykey);

        foreach(string myvalue in mySortedList.Values)
            Console.WriteLine("Key = " + myvalue);
    }
}
```

**错误:**

> 未处理异常:
> 系统。ArgumentOutOfRangeException:索引超出范围。必须是非负的，并且小于集合的大小。
> 参数名称:索引

**注:**

*   索引序列基于排序序列。当一个元素被添加时，它会以正确的排序顺序被插入到 SortedList 中，索引也会相应地进行调整。当元素被移除时，索引也会相应地调整。因此，特定键/值对的索引可能会随着从 SortedList 对象中添加或删除元素而改变。
*   这个方法是一个 O(n)运算，其中 n 是 Count。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . sorted list . remove at？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.sortedlist.removeat?view=netframework-4.7.2)