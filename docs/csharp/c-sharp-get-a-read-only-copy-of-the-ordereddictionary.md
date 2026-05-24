# C# |获取 OrderedDictionary 的只读副本

> 原文:[https://www . geesforgeks . org/c-sharp-get-a-read-only-copy-the-ordered dictionary/](https://www.geeksforgeeks.org/c-sharp-get-a-read-only-copy-of-the-ordereddictionary/)

**OrderedDictionary。AsReadOnly** 方法返回当前 OrderedDictionary 集合的只读副本。

**语法:**

```cs
public System.Collections.Specialized.OrderedDictionary AsReadOnly ();

```

**返回值:**当前 OrderedDictionary 集合的只读副本。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to get a read-only
// copy of the OrderedDictionary
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

        // To Get a read-only copy of
        // the OrderedDictionary
        OrderedDictionary myDict_1 = myDict.AsReadOnly();

        // Checking if myDict_1 is read-only
        Console.WriteLine(myDict_1.IsReadOnly);
    }
}
```

**输出:**

```cs
True

```

**例 2:**

```cs
// C# code to get a read-only
// copy of the OrderedDictionary
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

        // To Get a read-only copy of
        // the OrderedDictionary
        OrderedDictionary myDict_1 = myDict.AsReadOnly();

        // Checking if myDict_1 is read-only
        Console.WriteLine(myDict_1.IsReadOnly);
    }
}
```

**输出:**

```cs
True

```

**注意:**AsReadOnly 方法在当前 OrderedDictionary 集合周围创建一个只读包装。对 OrderedDictionary 集合所做的更改会反映在只读副本中。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . orderedddictionary . as readonly？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.ordereddictionary.asreadonly?view=netframework-4.7.2)