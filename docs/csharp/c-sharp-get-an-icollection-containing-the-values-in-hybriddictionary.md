# C# |获取包含混合字典

中的值的集合

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-an-I collection-包含混合字典中的值/](https://www.geeksforgeeks.org/c-sharp-get-an-icollection-containing-the-values-in-hybriddictionary/)

**杂交词典。Values** 属性用于获取包含混合字典中的值的集合。

**语法:**

```cs
public System.Collections.ICollection Values { get; }

```

**返回值:**它返回一个包含混合字典中的值的[集合](https://docs.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=netframework-4.7.2)。

以下程序说明了**混合词典的使用。值**属性:

**例 1:**

```cs
// C# code to get an ICollection containing
// the values in the HybridDictionary.
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

        // copying the Values in HybridDictionary
        // to a one-dimensional Array instance
        // at the specified index.
        myDict.Values.CopyTo(myArr, 0);

        // To get an ICollection containing
        // the Values in the HybridDictionary
        for (int i = 0; i < myDict.Count; i++)
            Console.WriteLine(myArr[i]);
    }
}
```

**输出:**

```cs
Apple
Banana
Cat
Dog
Elephant
Fish

```

**例 2:**

```cs
// C# code to get an ICollection containing
// the values in the HybridDictionary.
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

        // copying the Values in HybridDictionary
        // to a one-dimensional Array instance
        // at the specified index.
        myDict.Values.CopyTo(myArr, 0);

        // To get an ICollection containing
        // the Values in the HybridDictionary
        for (int i = 0; i < myDict.Count; i++)
            Console.WriteLine(myArr[i]);
    }
}
```

**输出:**

```cs
first
second
third
fourth
fifth

```

**注:**

*   icocollection 中值的顺序未指定，但它与由 ***Keys*** 方法返回的 icocollection 中关联键的顺序相同。
*   返回的 ICollection 不是静态副本。相反，ICollection 引用了原始混合字典中的值。因此，对混合词典的更改将继续反映在 ICollection 中。
*   检索该属性的值是一个 O(1)操作。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . hybrid dictionary . values？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.hybriddictionary.values?view=netframework-4.7.2)