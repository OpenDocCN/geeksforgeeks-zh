# C# |创建一个指定大小写的空混合字典

> 原文:[https://www . geesforgeks . org/c-sharp-creating-empty-hybrid dictionary-with-specificated-区分大小写/](https://www.geeksforgeeks.org/c-sharp-creating-an-empty-hybriddictionary-with-specified-case-sensitivity/)

**杂交字典(布尔值)**构造函数创建一个指定大小写的空杂交字典。

**语法:**

```cs
public HybridDictionary (bool caseInsensitive);

```

这里， ***【不区分大小写】*** 是一个布尔值，表示混合字典是否不区分大小写。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to create an empty
// HybridDictionary with the
// specified case sensitivity.
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an empty HybridDictionary
        // with the specified case sensitivity.
        HybridDictionary myDict = new HybridDictionary(false);

        // Adding key/value pairs in myDict
        myDict.Add("I", "first");
        myDict.Add("i", "first");
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
i first
II second
III third
IV fourth
V fifth

```

**例 2:**

```cs
// C# code to create an empty
// HybridDictionary with the
// specified case sensitivity.
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an empty HybridDictionary
        // with the specified case sensitivity.
        HybridDictionary myDict = new HybridDictionary(true);

        // Adding key/value pairs in myDict
        myDict.Add("A", "Apple");
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

**运行时错误:**

> 未处理异常:
> 系统。参数异常:具有相同键的条目已经存在。
> 在系统中。收藏。专业。列表词典。添加

**注意:**这个构造函数是一个 O(1)运算。