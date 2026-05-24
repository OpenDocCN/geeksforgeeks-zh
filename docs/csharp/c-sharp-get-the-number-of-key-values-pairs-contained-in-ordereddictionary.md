# C# |获取 OrderedDictionary

中包含的键/值对的数量

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-number-of-key-values-pairs-contained-in-ordered dictionary/](https://www.geeksforgeeks.org/c-sharp-get-the-number-of-key-values-pairs-contained-in-ordereddictionary/)

**OrderedDictionary。Count** 属性用于获取 OrderedDictionary 集合中包含的键/值对的数量。

**语法:**

```cs
public int Count { get; }

```

**返回值:**ordered dictionary 集合中包含的键/值对的数量。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to get the number of
// key/values pairs contained
// in the OrderedDictionary
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

        // To Get the number of key/values
        // pairs contained in the OrderedDictionary
        Console.WriteLine("Number of key/value pairs are : " 
                                            + myDict.Count);
    }
}
```

**输出:**

```cs
Number of key/value pairs are : 5

```

**例 2:**

```cs
// C# code to get the number of
// key/values pairs contained
// in the OrderedDictionary
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

        // To Get the number of key/values
        // pairs contained in the OrderedDictionary
        Console.WriteLine("Number of key/value pairs are : " 
                                            + myDict.Count);
    }
}
```

**输出:**

```cs
Number of key/value pairs are : 4

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . ordered dictionary . count？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.ordereddictionary.count?view=netframework-4.7.2)