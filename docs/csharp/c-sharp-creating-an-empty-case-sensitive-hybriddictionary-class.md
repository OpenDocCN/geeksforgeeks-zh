# C# |创建一个空的区分大小写的混合字典类

> 原文:[https://www . geesforgeks . org/c-sharp-creating-a-empty-区分大小写-hybriddictionary-class/](https://www.geeksforgeeks.org/c-sharp-creating-an-empty-case-sensitive-hybriddictionary-class/)

**杂交词典()**创建一个空的 ***区分大小写的*** 杂交词典。

**语法:**

```cs
public HybridDictionary ();

```

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to create an empty
// case-sensitive HybridDictionary.
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an empty case-sensitive
        // HybridDictionary named myDict
        HybridDictionary myDict = new HybridDictionary();

        // Adding key/value pairs in myDict
        myDict.Add("I", "first");
        myDict.Add("II", "second");
        myDict.Add("III", "third");
        myDict.Add("IV", "fourth");
        myDict.Add("V", "fifth");

        // Displaying the key/value pairs in myDict
        foreach(DictionaryEntry de in myDict)
            Console.WriteLine(de.Key + " " + de.Value);
    }
}
```

**输出:**

```cs
I first
II second
III third
IV fourth
V fifth

```

**例 2:**

```cs
// C# code to create an empty
// case-sensitive HybridDictionary.
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an empty case-sensitive
        // HybridDictionary named myDict
        HybridDictionary myDict = new HybridDictionary();

        // Adding key/value pairs in myDict
        myDict.Add("A", "Apple");

        // To show that the HybridDictionary is
        // case-sensitive
        myDict.Add("a", "Air");
        myDict.Add("B", "Banana");
        myDict.Add("C", "Cat");
        myDict.Add("D", "Dog");
        myDict.Add("d", "Dolphine");
        myDict.Add("E", "Elephant");
        myDict.Add("F", "Fish");

        // Displaying the key/value pairs in myDict
        foreach(DictionaryEntry de in myDict)
            Console.WriteLine(de.Key + " " + de.Value);
    }
}
```

**输出:**

```cs
A Apple
a Air
B Banana
C Cat
D Dog
d Dolphine
E Elephant
F Fish

```

**注:**

*   默认情况下，集合区分大小写。
*   比较器确定两个键是否相等。混合字典中的每个键都必须是唯一的。
*   这个构造函数是一个 O(1)运算。

**参考:**

*   https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.hybriddictionary.-ctor?view=netframework-4.7.2# System_Collections_Specialized_HybridDictionary__ctor