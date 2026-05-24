# C# |计算混合字典

中键/值对的数量

> 原文:[https://www . geesforgeks . org/c-sharp-count-number-of-key-value-pairs-in-hybrid dictionary/](https://www.geeksforgeeks.org/c-sharp-count-the-number-of-key-value-pairs-in-hybriddictionary/)

**杂交词典。Count** 属性用于获取混合字典中包含的键/值对的数量。

**语法:**

```cs
public int Count { get; }

```

**返回值:**混合字典中包含的键/值对的数量。

**注意:**检索该属性的值是一个 O(1)运算。

以下程序说明了**混合词典的使用。计数**属性:

**例 1:**

```cs
// C# code to get the number of key/value
// pairs contained in the HybridDictionary.
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
        myDict.Add("Australia", "Canberra");
        myDict.Add("Belgium", "Brussels");
        myDict.Add("Netherlands", "Amsterdam");
        myDict.Add("China", "Beijing");
        myDict.Add("Russia", "Moscow");
        myDict.Add("India", "New Delhi");

        // To get count of key/value pairs in myDict
        Console.WriteLine("Total key/value pairs in myDict are : " 
                                                  + myDict.Count);
    }
}
```

**输出:**

```cs
Total key/value pairs in myDict are : 6

```

**例 2:**

```cs
// C# code to get the number of key/value
// pairs contained in the HybridDictionary.
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

        // To get count of key/value pairs in myDict
        Console.WriteLine("Total key/value pairs in myDict are : " 
                                                   + myDict.Count);
    }
}
```

**输出:**

```cs
Total key/value pairs in myDict are : 5

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . hybrid dictionary . count？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.hybriddictionary.count?view=netframework-4.7.2)