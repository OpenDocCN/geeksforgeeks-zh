# C# |将键和值添加到 OrderedDictionary 集合中

> 原文:[https://www . geesforgeks . org/c-sharp-add-key-value-to-ordered dictionary-collection/](https://www.geeksforgeeks.org/c-sharp-add-key-and-value-into-ordereddictionary-collection/)

**OrderedDictionary。Add(Object，Object)** 方法用于将具有指定键和值的条目添加到具有最低可用索引的 OrderedDictionary 集合中。

**语法:**

```cs
public void Add (object key, object value);

```

**参数:**

> **键:**要添加的条目的键。
> **值:**条目添加的值。该值可以为空。

**异常:**

*   **NotSupportedException :** 如果 OrderedDictionary 集合是只读的。
*   **ArgumentException :** 如果 OrderedDictionary 集合中已经存在具有相同键的元素。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to add key and value
// into OrderedDictionary
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

        // Displaying the number of key/value
        // pairs in myDict
        Console.WriteLine(myDict.Count);

        // Displaying the key/value pairs in myDict
        foreach(DictionaryEntry de in myDict)
            Console.WriteLine(de.Key + " --> " + de.Value);
    }
}
```

**输出:**

```cs
5
key1 --> value1
key2 --> value2
key3 --> value3
key4 --> value4
key5 --> value5

```

**例 2:**

```cs
// C# code to add key and value
// into OrderedDictionary
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

        // This should raise "ArgumentException"
        // as an element with the same key already
        // exists in the OrderedDictionary collection.
        myDict.Add("key2", "value3");
        myDict.Add("key4", "value4");
        myDict.Add("key5", "value5");

        // Displaying the number of key/value
        // pairs in myDict
        Console.WriteLine(myDict.Count);

        // Displaying the key/value pairs in myDict
        foreach(DictionaryEntry de in myDict)
            Console.WriteLine(de.Key + " --> " + de.Value);
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。参数异常:项目已经添加。字典中的键:“key2”正在添加的键:“key2”

**注意:**一个键不能为空，但一个值可以为空。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . ordered dictionary . add？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.ordereddictionary.add?view=netframework-4.7.2)