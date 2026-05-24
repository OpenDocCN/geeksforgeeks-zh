# C# |创建具有指定初始大小写的混合字典&区分大小写

> 原文:[https://www . geesforgeks . org/c-sharp-creating-a-hybrid dictionary-with-specified-size-区分大小写/](https://www.geeksforgeeks.org/c-sharp-creating-a-hybriddictionary-with-specified-initial-size-case-sensitivity/)

**杂交字典(Int32，布尔值)**创建具有指定初始大小写和区分大小写的杂交字典。

**语法:**

```cs
public HybridDictionary (int initialSize, bool caseInsensitive);

```

**参数:**

*   **initialSize :** 混合字典最初可以包含的条目的大致数量。
*   **不区分大小写:**表示杂交字典是否不区分大小写的布尔值。

以下程序说明了**混合字典(Int32，布尔值)**的使用:

**例 1:**

```cs
// C# code to create a HybridDictionary
// with the specified initial size
// and case sensitivity.
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HybridDictionary with the
        // specified initial size and case sensitivity.
        HybridDictionary myDict = new HybridDictionary(10, false);

        // Adding key/value pairs in myDict
        myDict.Add("I", "first");

        // This will not raise exception as the
        // Collection is not case-insensitive
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
III third
V fifth
II second
i first
I first
IV fourth

```

**例 2:**

```cs
// C# code to create a HybridDictionary
// with the specified initial size
// and case sensitivity.
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HybridDictionary with the
        // specified initial size and case sensitivity.
        HybridDictionary myDict = new HybridDictionary(10, true);

        // Adding key/value pairs in myDict
        myDict.Add("A", "Apple");

        // This will raise exception as the
        // Collection is case-insensitive
        myDict.Add("a", "Air");
        myDict.Add("B", "Banana");
        myDict.Add("C", "Cat");
        myDict.Add("D", "Dog");
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
> 系统。参数异常:项目已经添加。字典中的关键字:“A”正在添加关键字:“A”【系统中的 T1】。集合。哈希表。插入

**注:**

*   如果集合的初始大小大于**列表字典**的最佳大小，则集合存储在**哈希表**中，以避免将元素从列表字典复制到哈希表的开销。
*   这个构造函数是一个 O(n)运算，其中 n 是 **initialSize** 。