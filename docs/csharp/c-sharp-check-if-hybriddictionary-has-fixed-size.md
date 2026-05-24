# C# |检查杂交词典是否有固定大小

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-hybrid dictionary-has-fixed-size/](https://www.geeksforgeeks.org/c-sharp-check-if-hybriddictionary-has-fixed-size/)

**杂交词典。IsFixedSize** 属性用于获取一个值，该值指示混合字典是否具有固定大小。

**语法:**

```cs
public bool IsFixedSize { get; }

```

**返回值:**该属性始终返回 ***false*** 。

以下是说明**杂交词典使用的程序。IsFixedSize** 属性:

**例 1:**

```cs
// C# code to check whether the
// HybridDictionary has a fixed size.
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
        // has a fixed size.
        Console.WriteLine(myDict.IsFixedSize);
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
// HybridDictionary has a fixed size.
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
        myDict.Add("key1", "value1");
        myDict.Add("key2", "value2");
        myDict.Add("key3", "value3");
        myDict.Add("key4", "value4");

        // To check whether the HybridDictionary
        // has a fixed size.
        Console.WriteLine(myDict.IsFixedSize);
    }
}
```

**输出:**

```cs
False

```

**注:**

*   具有固定大小的集合不允许在创建集合后添加或移除元素，但允许修改现有元素。
*   检索该属性的值是一个 **O(1)** 操作。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . hybrid dictionary . is fixed size？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.hybriddictionary.isfixedsize?view=netframework-4.7.2)