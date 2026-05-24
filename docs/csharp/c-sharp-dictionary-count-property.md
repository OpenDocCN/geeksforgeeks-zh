# C# |字典。计数属性

> 原文:[https://www . geesforgeks . org/c-sharp-dictionary-count-property/](https://www.geeksforgeeks.org/c-sharp-dictionary-count-property/)

此属性用于获取字典中包含的键/值对的数量。

**语法:**

```cs
public int Count { get; }

```

**返回值:**字典中包含的键/值对的数量。

以下是说明上述属性使用的程序:

**例 1:**

```cs
// C# code to count the number of 
// key/value pairs in  Dictionary
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Create a new dictionary of
        // strings, with string keys.
        Dictionary<string, string> myDict = 
           new Dictionary<string, string>();

        // Adding key/value pairs in myDict
        myDict.Add("Australia", "Canberra");
        myDict.Add("Belgium", "Brussels");
        myDict.Add("Netherlands", "Amsterdam");
        myDict.Add("China", "Beijing");
        myDict.Add("Russia", "Moscow");
        myDict.Add("India", "New Delhi");

        // To get count of key/value
        // pairs in myDict
        Console.WriteLine("Total key/value pairs"+
              " in myDict are : " + myDict.Count);
    }
}
```

**Output:**

```cs
Total key/value pairs in myDict are : 6

```

**例 2:**

```cs
// C# code to count the number of 
// key/value pairs in  Dictionary
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Create a new dictionary of 
        // strings, with string keys.
        Dictionary<int, string> myDict = 
          new Dictionary<int, string>();

        // Adding key/value pairs in myDict
        myDict.Add(1, "C");
        myDict.Add(2, "C++");
        myDict.Add(3, "Java");
        myDict.Add(4, "Python");
        myDict.Add(5, "C#");
        myDict.Add(6, "HTML");

        // To get count of key/value pairs in myDict
        Console.WriteLine("Total key/value pairs"+
              " in myDict are : " + myDict.Count);
    }
}
```

**Output:**

```cs
Total key/value pairs in myDict are : 6

```

**注意:**检索该属性的值是一个 O(1)运算。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . dictionary-2 . count？view = net framework-4 . 7 . 2 # System _ Collections _ Generic _ Dictionary _ 2 _ Count](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.dictionary-2.count?view=netframework-4.7.2# System_Collections_Generic_Dictionary_2_Count)