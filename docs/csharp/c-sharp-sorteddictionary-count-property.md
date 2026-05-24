# C# | SortedDictionary。计数属性

> 原文:[https://www . geeksforgeeks . org/c-sharp-sorted dictionary-count-property/](https://www.geeksforgeeks.org/c-sharp-sorteddictionary-count-property/)

此属性用于获取包含在*排序字典< TKey、TVaLue>T1 中的键/值对的数量。*

**语法:**

```cs
public int Count { get; }

```

**返回值:**返回 SortedDictionary 中包含的键/值对的个数。

以下是说明上述属性使用的程序:

**例 1:**

```cs
// C# code to count the number of
// key/value pairs in SortedDictionary
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Create a new SortedDictionary of
        // int, with int keys.
        SortedDictionary<int, int> myDict = 
           new SortedDictionary<int, int>();

        // Adding key/value pairs in myDict
        myDict.Add(9, 8);
        myDict.Add(3, 4);
        myDict.Add(4, 7);
        myDict.Add(1, 7);

        // To get count of key/value pairs in myDict
        Console.WriteLine("Total key/value pairs "
              + "in myDict are : " + myDict.Count);
    }
}
```

**Output:**

```cs
Total key/value pairs in myDict are : 4

```

**例 2:**

```cs
// C# code to count the number of
// key/value pairs in  SortedDictionary
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Create a new dictionary of
        // strings, with string keys.
        SortedDictionary<string, string> myDict = 
          new SortedDictionary<string, string>();

        // Adding key/value pairs in myDict
        myDict.Add("Australia", "Canberra");
        myDict.Add("Belgium", "Brussels");
        myDict.Add("Netherlands", "Amsterdam");
        myDict.Add("China", "Beijing");
        myDict.Add("Russia", "Moscow");
        myDict.Add("India", "New Delhi");

        // To get count of key/value pairs in myDict
        Console.WriteLine("Total key/value pairs "
              + "in myDict are : " + myDict.Count);
    }
}
```

**Output:**

```cs
Total key/value pairs in myDict are : 6

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . sorted dictionary-2 . count？view = net framework-4 . 7 . 2 # System _ Collections _ Generic _ sorted dictionary _ 2 _ Count](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sorteddictionary-2.count?view=netframework-4.7.2# System_Collections_Generic_SortedDictionary_2_Count)