# C# 获取包含混合字典中关键字的集合

> 原文：[https://www.geeksforgeeks.org/c-sharp-get-an-icollection-containing-the-keys-in-hybriddictionary/](https://www.geeksforgeeks.org/c-sharp-get-an-icollection-containing-the-keys-in-hybriddictionary/)

`HybridDictionary.Keys` 属性用于获取包含混合字典中的键的 `ICollection`。

## 语法

```cs
public System.Collections.ICollection Keys { get; }
```

## 返回值
它返回一个包含混合字典中的键的 [`ICollection`](https://docs.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=netframework-4.7.2)。

以下程序说明了 `HybridDictionary.Keys` 属性的使用：

## 示例 1

```cs
// C# code to get an ICollection containing
// the keys in the HybridDictionary.
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

        // Creating a String arr named myArr
        String[] myArr = new String[myDict.Count];

        // copying the Keys in HybridDictionary
        // to a one-dimensional Array instance
        // at the specified index.
        myDict.Keys.CopyTo(myArr, 0);

        // To get an ICollection containing
        // the keys in the HybridDictionary
        for (int i = 0; i < myDict.Count; i++)
            Console.WriteLine(myArr[i]);
    }
}
```

## 输出

```cs
A
B
C
D
E
F
```

## 示例 2

```cs
// C# code to get an ICollection containing
// the keys in the HybridDictionary.
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

        // Creating a String arr named myArr
        String[] myArr = new String[myDict.Count];

        // copying the Keys in HybridDictionary
        // to a one-dimensional Array instance
        // at the specified index.
        myDict.Keys.CopyTo(myArr, 0);

        // To get an ICollection containing
        // the keys in the HybridDictionary
        for (int i = 0; i < myDict.Count; i++)
            Console.WriteLine(myArr[i]);
    }
}
```

## 输出

```cs
I
II
III
IV
V
```

## 注

*   `ICollection` 中值的顺序未指定，但它与 `Values` 属性返回的 `ICollection` 中关联值的顺序相同。
*   返回的 `ICollection` 不是静态副本。取而代之的是，`ICollection` 指的是原始混合字典中的键。因此，对混合词典的更改将继续反映在 `ICollection` 中。
*   检索该属性的值是一个 O(1) 操作。

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.hybriddictionary.keys?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.hybriddictionary.keys?view=netframework-4.7.2)