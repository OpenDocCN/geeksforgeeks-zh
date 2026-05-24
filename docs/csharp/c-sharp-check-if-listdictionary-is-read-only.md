# C# |检查列表字典是否为只读

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-list dictionary-只读/](https://www.geeksforgeeks.org/c-sharp-check-if-listdictionary-is-read-only/)

**列表词典。IsReadOnly** 属性用于获取一个值，该值指示列表字典是否是只读的。

**语法:**

```cs
public bool IsReadOnly { get; }

```

**返回值:**该属性始终返回 ***false*** 。

**例:**

```cs
// C# code to check if ListDictionary is read-only
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

        // Checking if ListDictionary is read-only
        Console.WriteLine(myDict.IsReadOnly);
    }
}
```

**输出:**

```cs
False

```

**注意:**

*   The read-only collection is not allowed to add, remove or modify elements after it is created.
*   A read-only collection is just a collection with a wrapper that prevents the collection from being modified. Therefore, if changes are made to the underlying collection, the read-only collection will reflect these changes.
*   Retrieving the value of this attribute is an O(1) operation.

**参考:**

*   [https://docs。微软。com/en-us/dotnet/API/system。收藏品。专业的。列表词典。是只读的。视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.listdictionary.isreadonly?view=netframework-4.7.2)