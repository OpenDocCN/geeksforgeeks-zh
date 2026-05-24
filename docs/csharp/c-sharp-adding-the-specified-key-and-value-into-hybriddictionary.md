# C# |将指定的键和值添加到混合字典中

> 原文:[https://www . geesforgeks . org/c-sharp-将指定的键和值添加到混合字典/](https://www.geeksforgeeks.org/c-sharp-adding-the-specified-key-and-value-into-hybriddictionary/)

**杂交词典。Add(Object，Object)** 方法用于将具有指定键和值的条目添加到混合字典中。

**语法:**

```cs
public void Add (object key, object value);

```

**参数:**

> **键:**要添加的条目的键。
> **值:**条目添加的值。该值可以为空。

**异常:**

*   **ArgumentNullException :** 如果密钥为空。
*   **参数异常:**如果混合字典中已经存在具有相同关键字的条目。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to add an entry with
// the specified key and value
// into the HybridDictionary.
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
        myDict.Add("Australia", "Canberra");
        myDict.Add("Belgium", "Brussels");
        myDict.Add("Netherlands", "Amsterdam");
        myDict.Add("China", "Beijing");
        myDict.Add("Russia", "Moscow");
        myDict.Add("India", "New Delhi");

        // To get count of key/value pairs in myDict
        Console.WriteLine("Total key/value pairs in myDict are : " 
                                                  + myDict.Count);

        // Displaying the key/value pairs in myDict
        Console.WriteLine("The key/value pairs in myDict are : ");

        foreach(DictionaryEntry de in myDict)
        {
            Console.WriteLine(de.Key + " --> " + de.Value);
        }
    }
}
```

**输出:**

```cs
Total key/value pairs in myDict are : 6
The key/value pairs in myDict are : 
Australia --> Canberra
Belgium --> Brussels
Netherlands --> Amsterdam
China --> Beijing
Russia --> Moscow
India --> New Delhi

```

**例 2:**

```cs
// C# code to add an entry with
// the specified key and value
// into the HybridDictionary.
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

        // To get count of key/value pairs in myDict
        Console.WriteLine("Total key/value pairs in myDict are : " 
                                                  + myDict.Count);

        // Displaying the key/value pairs in myDict
        Console.WriteLine("The key/value pairs in myDict are : ");

        foreach(DictionaryEntry de in myDict)
        {
            Console.WriteLine(de.Key + " --> " + de.Value);
        }
    }
}
```

**输出:**

```cs
Total key/value pairs in myDict are : 5
The key/value pairs in myDict are : 
I --> first
II --> second
III --> third
IV --> fourth
V --> fifth

```

**注:**

*   一个对象，如果它的状态和它的哈希代码值之间没有相关性，那么它通常不应该被用作键。例如，字符串对象比字符串构建器对象更适合用作键。
*   键不能为空，但值可以为空。
*   这个方法是一个 O(1)运算。
*   当元素数量大于**列表词典**的最佳大小时，元素将从列表词典复制到**哈希表**中。然而，这种情况只会发生一次。如果集合已经存储在哈希表中，并且元素数量低于列表字典的最佳大小，则集合将保留在哈希表中。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . hybrid dictionary . add？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.hybriddictionary.add?view=netframework-4.7.2)