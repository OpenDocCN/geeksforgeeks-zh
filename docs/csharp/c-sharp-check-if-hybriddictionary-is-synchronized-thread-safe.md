# C# |检查混合字典是否同步(线程安全)

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-hybrid dictionary-is-synchronized-thread-safe/](https://www.geeksforgeeks.org/c-sharp-check-if-hybriddictionary-is-synchronized-thread-safe/)

**杂交词典。IsSynchronized** 属性用于获取一个值，该值指示混合字典是否同步(线程安全)。

**语法:**

```cs
public bool IsSynchronized { get; }

```

**返回值:**该属性始终返回 ***false*** 。

以下程序说明了**混合词典的使用。同步**属性:

**例 1:**

```cs
// C# code to check whether the
// HybridDictionary is synchronized
// (thread safe).
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
        myDict.Add("I", "first");
        myDict.Add("II", "second");
        myDict.Add("III", "third");
        myDict.Add("IV", "fourth");
        myDict.Add("V", "fifth");

        // To check whether the HybridDictionary
        // is synchronized (thread safe).
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
// C# code to check whether the
// HybridDictionary is synchronized
// (thread safe).
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
        myDict.Add("key5", "value5");

        // To check whether the HybridDictionary
        // is synchronized (thread safe).
        Console.WriteLine(myDict.IsSynchronized);
    }
}
```

**输出:**

```cs
False

```

**注意:**枚举集合本质上不是一个线程安全的过程。即使同步了集合，其他线程仍然可以修改集合，这将导致枚举数引发异常。为了保证枚举期间的线程安全，可以在整个枚举期间锁定集合，也可以捕获由其他线程所做的更改导致的异常。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . hybrid dictionary . is synchronized？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.hybriddictionary.issynchronized?view=netframework-4.7.2)