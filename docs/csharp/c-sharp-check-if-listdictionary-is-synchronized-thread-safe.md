# C# |检查 ListDictionary 是否同步(线程安全)

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-list dictionary-is-synchronized-thread-safe/](https://www.geeksforgeeks.org/c-sharp-check-if-listdictionary-is-synchronized-thread-safe/)

**列表词典。IsSynchronized** 属性用于获取一个值，该值指示列表字典是否同步(线程安全)。

**语法:**

```cs
public bool IsSynchronized { get; }

```

**返回值:**该属性始终返回 ***false*** 。

以下是说明**列表词典使用的程序。同步**属性:

**例 1:**

```cs
// C# code to check if ListDictionary
// is synchronized (thread safe)
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

        // Check if ListDictionary is
        // synchronized (thread safe)
        Console.WriteLine(myDict.IsSynchronized);
    }
}
```

**输出:**

```cs
False

```

**例 2:**

```cs
// C# code to check if ListDictionary
// is synchronized (thread safe)
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a ListDictionary named myDict
        ListDictionary myDict = new ListDictionary();

        myDict.Add("1", "C");
        myDict.Add("2", "C++");
        myDict.Add("3", "Java");
        myDict.Add("4", "Python");
        myDict.Add("5", "C#");
        myDict.Add("6", "Data Structure");

        // Check if ListDictionary is
        // synchronized (thread safe)
        Console.WriteLine(myDict.IsSynchronized);
    }
}
```

**输出:**

```cs
False

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . list dictionary . is synchronized？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.listdictionary.issynchronized?view=netframework-4.7.2)