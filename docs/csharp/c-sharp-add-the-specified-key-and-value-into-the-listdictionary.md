# C# |将指定的键和值添加到列表字典

> 原文:[https://www . geesforgeks . org/c-sharp-将指定的键和值添加到列表字典中/](https://www.geeksforgeeks.org/c-sharp-add-the-specified-key-and-value-into-the-listdictionary/)

**列表词典。Add(Object，Object)** 方法用于将具有指定键和值的条目添加到 ListDictionary 中。

**语法:**

```cs
public void Add (object key, object value);

```

**参数:**

> **键:**要添加的条目的键。
> **值:**条目添加的值。该值可以为空。

**异常:**

*   **ArgumentNullException :** 如果密钥为空。
*   **ArgumentException :** 是列表字典中已经存在的具有相同关键字的条目。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to add an entry with
// the specified key and value
// into the ListDictionary
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

        // Displaying the total number of elements in myDict
        Console.WriteLine("Total number of elements in myDict are : " 
                                                      + myDict.Count);

        // Displaying the elements in ListDictionary myDict
        foreach(DictionaryEntry de in myDict)
        {
            Console.WriteLine(de.Key + " " + de.Value);
        }
    }
}
```

**输出:**

```cs
Total number of elements in myDict are : 6
Australia Canberra
Belgium Brussels
Netherlands Amsterdam
China Beijing
Russia Moscow
India New Delhi

```

**例 2:**

```cs
// C# code to add an entry with
// the specified key and value
// into the ListDictionary
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

        // This should raise "ArgumentNullException"
        // as key is null
        myDict.Add(null, "Amsterdam");

        myDict.Add("China", "Beijing");
        myDict.Add("Russia", "Moscow");
        myDict.Add("India", "New Delhi");

        // Displaying the total number of elements in myDict
        Console.WriteLine("Total number of elements in myDict are : "
                                                     + myDict.Count);

        // Displaying the elements in ListDictionary myDict
        foreach(DictionaryEntry de in myDict)
        {
            Console.WriteLine(de.Key + " " + de.Value);
        }
    }
}
```

**输出:**

> 未处理异常:
> 系统。ArgumentNullException:键不能为空。
> 参数名称:键

**注:**

*   一个对象，如果它的状态和它的哈希代码值之间没有相关性，那么它通常不应该被用作键。例如，字符串对象比字符串构建器对象更适合用作键。
*   这个方法是一个 O(n)运算，其中 n 是 Count。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . list dictionary . add？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.listdictionary.add?view=netframework-4.7.2)