# C# | SortedDictionary。移除()方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-sorted dictionary-remove-method/](https://www.geeksforgeeks.org/c-sharp-sorteddictionary-remove-method/)

此方法用于从*排序字典< TKey、TVaLue>T1 中删除带有指定键的值。*

**语法:**

```cs
public bool Remove (TKey key);

```

**返回值:**如果成功找到并移除元素，此方法返回*true*；否则返回*假*。如果在 SortedDictionary 中没有找到关键字，该方法返回 *false* 。

**异常:**如果*键*为空，该方法将给出*参数异常*。

以下是说明上述方法使用的程序:

**例 1:**

```cs
// C# code to remove the entry with
// the specified key from the
// SortedDictionary
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
        Console.WriteLine("Total key/value pairs"
            + " in myDict are : " + myDict.Count);

        // Remove the entry with the specified
        // key from the Dictionary
        myDict.Remove("Russia");

        Console.WriteLine("After remove operation");

        // To get count of key/value pairs in myDict
        Console.WriteLine("Total key/value pairs"
           + " in myDict are : " + myDict.Count);
    }
}
```

**Output:**

```cs
Total key/value pairs in myDict are : 6
After remove operation
Total key/value pairs in myDict are : 5

```

**例 2:**

```cs
// C# code to remove the entry with
// the specified key from the
// SortedDictionary
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Create a new SortedDictionary
        // of ints, with int keys.
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

        // Remove the entry with the specified
        // key from the Dictionary
        myDict.Remove(9);

        Console.WriteLine("After remove operation");

        // To get count of key/value pairs in myDict
        Console.WriteLine("Total key/value pairs in"
                 + " myDict are : " + myDict.Count);
    }
}
```

**Output:**

```cs
Total key/value pairs in myDict are : 4
After remove operation
Total key/value pairs in myDict are : 3

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . sorted dictionary-2 . remove？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sorteddictionary-2.remove?view=netframework-4.7.2)