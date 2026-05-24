# C# |获取包含有序字典中的键的集合

> 原文:[https://www . geesforgeks . org/c-sharp-get-an-I collection-containing-key-in-ordered dictionary/](https://www.geeksforgeeks.org/c-sharp-get-an-icollection-containing-keys-in-ordereddictionary/)

**OrderedDictionary。Keys** 属性用于获取一个[集合](https://docs.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=netframework-4.7.2)对象，该对象包含 OrderedDictionary 集合中的键。

**语法:**

```cs
public System.Collections.ICollection Keys { get; }

```

**返回值:**它返回一个包含 OrderedDictionary 集合中的键的[集合](https://docs.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=netframework-4.7.2)对象。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to get an ICollection
// containing the keys in OrderedDictionary
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

        // Getting an ICollection containing
        // the keys in OrderedDictionary
        ICollection keyCollection = myDict.Keys;

        // Creating a String array
        String[] myKeys = new String[myDict.Count];

        // Copying the OrderedDictionary elements to
        // a one-dimensional Array object at the
        // specified index.
        keyCollection.CopyTo(myKeys, 0);

        for (int i = 0; i < myDict.Count; i++) {
            Console.WriteLine(myKeys[i]);
        }
    }
}
```

**输出:**

```cs
key1
key2
key3
key4
key5

```

**例 2:**

```cs
// C# code to get an ICollection
// containing the keys in OrderedDictionary
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
        myDict.Add("A", "Apple");
        myDict.Add("B", "Banana");
        myDict.Add("C", "Cat");
        myDict.Add("D", "Dog");

        // Getting an ICollection containing
        // the keys in OrderedDictionary
        ICollection keyCollection = myDict.Keys;

        // Creating a String array
        String[] myKeys = new String[myDict.Count];

        // Copying the OrderedDictionary elements to
        // a one-dimensional Array object at the
        // specified index.
        keyCollection.CopyTo(myKeys, 0);

        for (int i = 0; i < myDict.Count; i++) {
            Console.WriteLine(myKeys[i]);
        }
    }
}
```

**输出:**

```cs
A
B
C
D

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . ordered dictionary . keys？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.ordereddictionary.keys?view=netframework-4.7.2)