# C# |检查杂交词典是否为只读

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-hybrid dictionary-只读/](https://www.geeksforgeeks.org/c-sharp-check-if-hybriddictionary-is-read-only/)

**杂交词典。IsReadOnly** 属性用于获取一个值，该值指示混合字典是否是只读的。

**语法:**

```cs
public bool IsReadOnly { get; }

```

**返回值:**该属性始终返回 ***false*** 。

以下程序说明了**混合词典的使用。以色列唯一**属性:

**例 1:**

```cs
// C# code to check whether the
// HybridDictionary is read-only.
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HybridDictionary named myDict
        HybridDictionary myDict = new HybridDictionary();

        // Adding key/value pairs in myDict
        myDict.Add("A", "Apple");
        myDict.Add("B", "Banana");
        myDict.Add("C", "Cat");
        myDict.Add("D", "Dog");
        myDict.Add("E", "Elephant");
        myDict.Add("F", "Fish");

        // To check whether the HybridDictionary
        // is read-only.
        Console.WriteLine(myDict.IsReadOnly);
    }
}
```

**输出:**

```cs
False

```

**例 2:**

```cs
// C# code to check whether the
// HybridDictionary is read-only.
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HybridDictionary named myDict
        HybridDictionary myDict = new HybridDictionary();

        // Adding key/value pairs in myDict
        myDict.Add("one", "1");
        myDict.Add("two", "2");
        myDict.Add("three", "3");
        myDict.Add("four", "4");

        // To check whether the HybridDictionary
        // is read-only.
        Console.WriteLine(myDict.IsReadOnly);
    }
}
```

**输出:**

```cs
False

```

**注:**

*   只读集合在创建后不允许添加、移除或修改元素。
*   检索该属性的值是一个 **O(1)** 操作。
*   只读集合只是一个带有防止修改集合的包装的集合。因此，如果对基础集合进行了更改，只读集合将反映这些更改。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . hybrid dictionary . is readonly？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.hybriddictionary.isreadonly?view=netframework-4.7.2)