# C# |检查列表字典是否有固定大小

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-list dictionary-has-a-fixed-size/](https://www.geeksforgeeks.org/c-sharp-check-if-listdictionary-has-a-fixed-size/)

**列表词典。IsFixedSize** 属性用于获取一个值，该值指示列表字典是否有固定的大小。

**语法:**

```cs
public bool IsFixedSize { get; }

```

**返回值:**该属性始终返回 ***false*** 。

**例:**

```cs
// C# code to check if ListDictionary
// has a fixed size
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a ListDictionary named myDict
        ListDictionary myDict = new ListDictionary();

        myDict.Add("Australia", "Canberra");
        myDict.Add("Belgium", "Brussels");
        myDict.Add("Netherlands", "Amsterdam");
        myDict.Add("China", "Beijing");
        myDict.Add("Russia", "Moscow");
        myDict.Add("India", "New Delhi");

        // Checking if ListDictionary has a fixed size
        Console.WriteLine(myDict.IsFixedSize);
    }
}
```

**输出:**

```cs
False

```

**注意:**

*   Fixed-size collections do not allow elements to be added or removed after the collection is created, but allow existing elements to be modified.
*   A fixed-size collection is just a collection with wrappers that prevent elements from being added and removed. Therefore, if changes are made to the underlying collection, including adding or removing elements, the fixed-size collection will reflect these changes.
*   Retrieving the value of this attribute is an O(1) operation.

**参考:**

*   [https://docs。微软。com/en-us/dotnet/API/system。收藏品。专业的。列表词典。是固定大小的吗？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.listdictionary.isfixedsize?view=netframework-4.7.2)