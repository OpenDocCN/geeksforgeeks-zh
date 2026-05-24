# C# | SortedDictionary。清除()方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-sorted dictionary-clear-method/](https://www.geeksforgeeks.org/c-sharp-sorteddictionary-clear-method/)

该方法用于从*排序字典< TKey、TVaLue>T1 中移除所有键/值对。*

**语法:**

```cs
public void Clear ();

```

以下是说明上述方法使用的程序:

**例 1:**

```cs
// C# code to remove all pairs
// from SortedDictionary
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

        // Remove all pairs from the Dictionary
        myDict.Clear();

        Console.WriteLine("After clear operation");

        // To get count of key/value pairs in myDict
        Console.WriteLine("Total key/value pairs in"
                + " myDict  are : " + myDict.Count);
    }
}
```

**输出:**

```cs
Total key/value pairs in myDict are : 6
After clear operation
Total key/value pairs in myDict  are : 0

```