# C# |获取列表字典

中包含的键/值对的数量

> 原文:[https://www . geesforgeks . org/c-sharp-get-number-of-key-value-pairs-contained-in-list dictionary/](https://www.geeksforgeeks.org/c-sharp-get-the-number-of-key-value-pairs-contained-in-listdictionary/)

**列表词典。Count** 属性用于获取列表字典中包含的键/值对的数量。

**语法:**

```cs
public int Count { get; }

```

**返回值:**列表字典中包含的键/值对的数量。

以下是说明**列表词典使用的程序。计数**属性:

**例 1:**

```cs
// C# code to get the number
// of key/value pairs contained
// in the ListDictionary
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a ListDictionary named myDict
        ListDictionary myDict = new ListDictionary();

        // Adding key/value pairs in myDict
        myDict.Add("Australia", "Canberra");
        myDict.Add("Belgium", "Brussels");
        myDict.Add("Netherlands", "Amsterdam");
        myDict.Add("China", "Beijing");
        myDict.Add("Russia", "Moscow");
        myDict.Add("India", "New Delhi");

        // Displaying the number of key/value
        // pairs contained in the ListDictionary
        Console.WriteLine(myDict.Count);
    }
}
```

**输出:**

```cs
6

```

**例 2:**

```cs
// C# code to get the number
// of key/value pairs contained
// in the ListDictionary
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a ListDictionary named myDict
        ListDictionary myDict = new ListDictionary();

        // Adding key/value pairs in myDict
        myDict.Add("I", "first");
        myDict.Add("II", "second");
        myDict.Add("III", "third");
        myDict.Add("IV", "fourth");
        myDict.Add("V", "fifth");

        // Displaying the number of key/value
        // pairs contained in the ListDictionary
        Console.WriteLine(myDict.Count);
    }
}
```

**输出:**

```cs
5

```

**注意:**检索该属性的值是一个 O(1)运算。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . list dictionary . count？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.listdictionary.count?view=netframework-4.7.2)