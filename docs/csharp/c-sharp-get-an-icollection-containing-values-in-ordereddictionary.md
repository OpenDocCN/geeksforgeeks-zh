# C# |获取包含有序字典中的值的集合

> 原文:[https://www . geesforgeks . org/c-sharp-get-an-I collection-contained-values-in-ordered dictionary/](https://www.geeksforgeeks.org/c-sharp-get-an-icollection-containing-values-in-ordereddictionary/)

**OrderedDictionary。Values** 属性用于获取一个包含 OrderedDictionary 集合中的值的[集合](https://docs.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=netframework-4.7.2)对象。

**语法:**

```cs
public System.Collections.ICollection Values { get; }

```

**返回值:**它返回一个包含 OrderedDictionary 集合中的值的[集合](https://docs.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=netframework-4.7.2)对象。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to get an ICollection
// containing the values in OrderedDictionary
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
        // the values in OrderedDictionary
        ICollection valueCollection = myDict.Values;

        // Creating a String array
        String[] myValues = new String[myDict.Count];

        // Copying the OrderedDictionary elements to
        // a one-dimensional Array object at the
        // specified index.
        valueCollection.CopyTo(myValues, 0);

        for (int i = 0; i < myDict.Count; i++) {
            Console.WriteLine(myValues[i]);
        }
    }
}
```

**输出:**

```cs
value1
value2
value3
value4
value5

```

**例 2:**

```cs
// C# code to get an ICollection
// containing the values in OrderedDictionary
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
        // the values in OrderedDictionary
        ICollection valueCollection = myDict.Values;

        // Creating a String array
        String[] myValues = new String[myDict.Count];

        // Copying the OrderedDictionary elements to
        // a one-dimensional Array object at the
        // specified index.
        valueCollection.CopyTo(myValues, 0);

        for (int i = 0; i < myDict.Count; i++) {
            Console.WriteLine(myValues[i]);
        }
    }
}
```

**输出:**

```cs
Apple
Banana
Cat
Dog

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . ordered dictionary . values？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.ordereddictionary.values?view=netframework-4.7.2)