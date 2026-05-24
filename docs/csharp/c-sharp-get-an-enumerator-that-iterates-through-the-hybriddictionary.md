# C# |获取一个遍历混合字典的枚举器

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-a-enumerator-in-iterating-through-the-hybrid dictionary/](https://www.geeksforgeeks.org/c-sharp-get-an-enumerator-that-iterates-through-the-hybriddictionary/)

**杂交词典。GetEnumerator** 方法用于返回一个 IDictionaryEnumerator，迭代遍历 HybridDictionary。

**语法:**

```cs
public System.Collections.IDictionaryEnumerator GetEnumerator ();

```

**返回值:**它为混合字典返回一个[接口枚举器](https://docs.microsoft.com/en-us/dotnet/api/system.collections.idictionaryenumerator?view=netframework-4.7.2)(一个枚举非通用字典元素的接口)。

以下程序说明了**混合词典的使用。GetEnumerator 方法**:

**例 1:**

```cs
// C# code to get an IDictionaryEnumerator
// that iterates through the HybridDictionary.
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HybridDictionary named myDict
        HybridDictionary myDict = new HybridDictionary();

        // Adding key/value pairs in myDict
        myDict.Add("A", "Apple");
        myDict.Add("B", "Banana");
        myDict.Add("C", "Cat");
        myDict.Add("D", "Dog");
        myDict.Add("E", "Elephant");
        myDict.Add("F", "Fish");

        // To get an IDictionaryEnumerator
        // for the HybridDictionary.
        IDictionaryEnumerator myEnumerator = myDict.GetEnumerator();

        // If MoveNext passes the end of the
        // collection, the enumerator is positioned
        // after the last element in the collection
        // and MoveNext returns false.
        while (myEnumerator.MoveNext())
            Console.WriteLine(myEnumerator.Key + " --> " 
                                  + myEnumerator.Value);
    }
}
```

**输出:**

```cs
A --> Apple
B --> Banana
C --> Cat
D --> Dog
E --> Elephant
F --> Fish

```

**例 2:**

```cs
// C# code to get an IDictionaryEnumerator
// that iterates through the HybridDictionary.
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HybridDictionary named myDict
        HybridDictionary myDict = new HybridDictionary();

        // Adding key/value pairs in myDict
        myDict.Add("I", "first");
        myDict.Add("II", "second");
        myDict.Add("III", "third");
        myDict.Add("IV", "fourth");
        myDict.Add("V", "fifth");

        // To get an IDictionaryEnumerator
        // for the HybridDictionary.
        IDictionaryEnumerator myEnumerator = myDict.GetEnumerator();

        // If MoveNext passes the end of the
        // collection, the enumerator is positioned
        // after the last element in the collection
        // and MoveNext returns false.
        while (myEnumerator.MoveNext())
            Console.WriteLine(myEnumerator.Key + " --> " 
                                  + myEnumerator.Value);
    }
}
```

**输出:**

```cs
I --> first
II --> second
III --> third
IV --> fourth
V --> fifth

```

**注:**

*   C# 语言的 **foreach** 语句隐藏了枚举器的复杂性。因此，建议使用 foreach，而不是直接操作枚举器。
*   枚举数可用于读取集合中的数据，但不能用于修改基础集合。
*   **当前**返回同一对象，直到调用**移动下一个**或**重置**为止。移动下一个将当前设置为下一个元素。
*   只要集合保持不变，枚举数就保持有效。如果对集合进行了更改，例如添加、修改或删除元素，枚举数将无法恢复地失效，并且其行为未定义。
*   这个方法是一个 O(1)运算。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . hybrid dictionary . getenumerator？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.hybriddictionary.getenumerator?view=netframework-4.7.2)