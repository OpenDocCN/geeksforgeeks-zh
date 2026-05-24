# C# |检查 OrderedDictionary 集合是否包含特定的键

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-ordered dictionary-collection-contains-a-specific-key/](https://www.geeksforgeeks.org/c-sharp-check-if-ordereddictionary-collection-contains-a-specific-key/)

**OrderedDictionary。Contains(Object)** 方法用于检查 OrderedDictionary 集合是否包含特定的键。

**语法:**

```cs
public bool Contains (object key);

```

在这里， ***键*** 是定位在 OrderedDictionary 集合中的键。

**返回值:**如果 OrderedDictionary 集合包含具有指定键的元素，则该方法返回 ***True*** ，否则返回 ***False*** 。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to check if OrderedDictionary
// collection contains a specific key
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver method
    public static void Main()
    {

        // Creating a orderedDictionary named myDict
        OrderedDictionary myDict = new OrderedDictionary();

        // Adding key and value in myDict
        myDict.Add("key1", "value1");
        myDict.Add("key2", "value2");
        myDict.Add("key3", "value3");
        myDict.Add("key4", "value4");
        myDict.Add("key5", "value5");

        // Checking if OrderedDictionary
        // collection contains a specific key
        Console.WriteLine(myDict.Contains("Key6"));
    }
}
```

**输出:**

```cs
False

```

**例 2:**

```cs
// C# code to check if OrderedDictionary
// collection contains a specific key
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver method
    public static void Main()
    {

        // Creating a orderedDictionary named myDict
        OrderedDictionary myDict = new OrderedDictionary();

        // Adding key and value in myDict
        myDict.Add("key1", "value1");
        myDict.Add("key2", "value2");
        myDict.Add("key3", "value3");
        myDict.Add("key4", "value4");
        myDict.Add("key5", "value5");

        // Displaying the key/value pairs in myDict
        foreach(DictionaryEntry de in myDict)
            Console.WriteLine(de.Key + " --> " + de.Value);

        // Checking if OrderedDictionary collection
        // contains a specific key
        if (myDict.Contains("key4"))
            myDict.Remove("key4");

        // Displaying the key/value pairs in myDict
        foreach(DictionaryEntry de in myDict)
            Console.WriteLine(de.Key + " --> " + de.Value);
    }
}
```

**输出:**

```cs
key1 --> value1
key2 --> value2
key3 --> value3
key4 --> value4
key5 --> value5
key1 --> value1
key2 --> value2
key3 --> value3
key5 --> value5

```

**注意:**如果密钥不存在或者密钥为空，使用**项【对象】**属性可以返回空值。使用**包含**方法确定 OrderedDictionary 集合中是否存在特定的键。

**参考:**
[https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . ordered dictionary . contains？视图=网络框架-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.ordereddictionary.contains?view=netframework-4.7.2)