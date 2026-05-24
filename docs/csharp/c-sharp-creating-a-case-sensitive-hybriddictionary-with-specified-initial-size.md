# C# |创建具有指定初始大小写的区分大小写的混合字典

> 原文:[https://www . geesforgeks . org/c-sharp-creating-区分大小写-hybrid dictionary-with-specified-initial-size/](https://www.geeksforgeeks.org/c-sharp-creating-a-case-sensitive-hybriddictionary-with-specified-initial-size/)

**杂交字典(Int32)** 构造函数用于创建一个具有指定初始大小写的 ***区分大小写的*** 杂交字典。

**语法:**

```cs
public HybridDictionary (int initialSize);

```

这里， ***initialSize*** 是混合词典最初可以包含的大约条目数。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to create a case-sensitive
// HybridDictionary with the specified
// initial size.
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // creating a case-sensitive HybridDictionary
        // with the specified initial size.
        HybridDictionary myDict = new HybridDictionary(10);

        // Adding key/value pairs in myDict
        myDict.Add("A", "Apple");

        // This will not raise exception as
        // By default, the collection is case-sensitive
        myDict.Add("a", "Air");
        myDict.Add("B", "Banana");
        myDict.Add("C", "Cat");
        myDict.Add("D", "Dog");

        // This will not raise exception as
        // By default, the collection is case-sensitive
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
B Banana
a Air
A Apple
d Dolphine
C Cat
E Elephant
F Fish
D Dog

```

**例 2:**

```cs
// C# code to create a case-sensitive
// HybridDictionary with the specified
// initial size.
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // creating a case-sensitive HybridDictionary
        // with the specified initial size.
        HybridDictionary myDict = new HybridDictionary(10);

        // Adding key/value pairs in myDict
        // As the HybridDictionary is case-sensitive
        // Therefore no exception is raised
        // Because "k1" & "K1" are taken as different keys
        // Similarly "k2" & "K2", "k3" & "K3"
        myDict.Add("k1", "v1");
        myDict.Add("K1", "v1");
        myDict.Add("k2", "v2");
        myDict.Add("K2", "v2");
        myDict.Add("k3", "v3");
        myDict.Add("K3", "v3");

        // Displaying the key/value pairs in myDict
        foreach(DictionaryEntry de in myDict)
            Console.WriteLine(de.Key + " " + de.Value);
    }
}
```

**输出:**

```cs
k3 v3
K3 v3
k2 v2
K2 v2
k1 v1
K1 v1

```

**注:**

*   如果集合的初始大小大于**列表字典**的最佳大小，则集合存储在**哈希表**中，以避免将元素从列表字典复制到哈希表的开销。
*   默认情况下，集合区分大小写。
*   混合字典中的每个键都必须是唯一的。
*   这个构造函数是一个 O(n)运算，其中 n 是 **initialSize** 。