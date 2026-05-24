# SortedList 与 SortedDictionary 在 C# 中的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-sortedlist-and-sorteddictionary-in-c-sharp/](https://www.geeksforgeeks.org/difference-between-sortedlist-and-sorteddictionary-in-c-sharp/)

## SortedList 简介

在 C# 中，`SortedList` 是根据键排序的键/值对的集合。默认情况下，此集合按升序对键/值对进行排序。它是泛型和非泛型集合类型。泛型 `SortedList` 在 `System.Collections.Generic` 命名空间中定义，而非泛型 `SortedList` 在 `System.Collections` 命名空间中定义。

**例：**

```csharp
// C# program to illustrate how
// to create a sortedlist
using System;
using System.Collections;

class GFG {

    // Main Method
    static public void Main()
    {
        // Creating a sortedlist
        // Using SortedList class
        SortedList my_Slist = new SortedList();

        // Adding key/value pairs in
        // SortedList using Add() method
        my_Slist.Add(1.02, "Dog");
        my_Slist.Add(1.07, "Cat");
        my_Slist.Add(1.04, "Rat");
        my_Slist.Add(1.01, "Bird");

        foreach(DictionaryEntry pair in my_Slist)
        {
            Console.WriteLine("{0} and {1}",
                      pair.Key, pair.Value);
        }
        Console.WriteLine();
    }
}
```

**输出：**

```csharp
1.01 and Bird
1.02 and Dog
1.04 and Rat
1.07 and Cat
```

## SortedDictionary 简介

在 C# 中，`SortedDictionary` 是一个泛型集合，用于以排序后的形式存储键/值对，并对键进行排序。`SortedDictionary` 在 `System.Collections.Generic` 命名空间中定义。它本质上是动态的，意味着排序后的字典的大小会根据需要而增长。

**示例：**

```csharp
// C# program to illustrate how
// to create a sorted dictionary
using System;
using System.Collections.Generic;

class GFG {

    // Main Method
    static public void Main()
    {
        // Creating sorted dictionary
        // Using SortedDictionary class
        SortedDictionary<int, string> My_sdict = 
            new SortedDictionary<int, string>();

        // Adding key/value pair in Sorted
        // Dictionary Using Add() method
        My_sdict.Add(004, "Roscosmos");
        My_sdict.Add(003, "ESA");
        My_sdict.Add(001, "NASA");
        My_sdict.Add(005, "ISRO");
        My_sdict.Add(002, "CNSA");
        Console.WriteLine("Top 5 space agencies 2018:");

        // Accessing the key/value pair of the
        // SortedDictionary Using foreach loop
        foreach(KeyValuePair<int, string> pair in My_sdict)
        {
            Console.WriteLine("Rank: {0} and Name: {1}",
                                  pair.Key, pair.Value);
        }
    }
}
```

**输出：**

```csharp
Top 5 space agencies 2018:
Rank: 1 and Name: NASA
Rank: 2 and Name: CNSA
Rank: 3 and Name: ESA
Rank: 4 and Name: Roscosmos
Rank: 5 and Name: ISRO
```

## 主要区别

以下是 `SortedList` 和 `SortedDictionary` 之间的一些区别：

| SortedList | SortedDictionary |
| :--- | :--- |
| `SortedList` 的内存开销较低。 | `SortedDictionary` 的内存开销较高。 |
| 在 `SortedList` 中，元素存储在内存中的连续块中。 | 在 `SortedDictionary` 中，元素存储在单独的对象中，这些对象可以遍布整个堆。 |
| 在 `SortedList` 中，内存碎片较低。 | 在 `SortedDictionary` 中，内存碎片较高。 |
| 它需要更少内存来存储。 | 它需要更多内存来存储。 |
| 在 `SortedList` 中，插入和删除操作较慢。 | 在 `SortedDictionary` 中，插入和删除操作较快。 |
| 在 `SortedList` 中，可以使用索引访问元素。 | 在 `SortedDictionary` 中，可以使用索引或键访问元素。这里键访问就足够了，不需要使用索引访问元素。 |
| 在 `SortedList` 中，数据已经是排序后的形式。 | 在 `SortedDictionary` 中，数据是未排序的形式。 |