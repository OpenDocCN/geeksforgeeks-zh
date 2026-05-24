# C# | SortedDictionary。密钥属性

> 原文:[https://www . geeksforgeeks . org/c-sharp-sorted dictionary-keys-property/](https://www.geeksforgeeks.org/c-sharp-sorteddictionary-keys-property/)

此属性用于获取包含 SortedDictionary 中的键的集合。

**语法:**

> 公共系统。集合。通用。排序字典<tkey>。KeyCollection Keys { get}</tkey>

**返回值:**它返回一个包含 SortedDictionary 中的键的集合。

下面是说明上述属性使用的程序:

**例 1:**

```cs
// C# code to get the keys
// in the SortedDictionary
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Create a new SortedDictionary
        // of strings, with string keys.
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

        // To get the keys alone,
        // use the Keys property.
        SortedDictionary<string, string>.KeyCollection keyColl = 
                                                    myDict.Keys;

        // The elements of the KeyCollection
        // are strongly typed with the type
        // that was specified for dictionary
        // keys
        foreach(string s in keyColl)
        {
            Console.WriteLine("Key = {0}", s);
        }
    }
}
```

**Output:**

```cs
Total key/value pairs in myDict are : 6
Key = Australia
Key = Belgium
Key = China
Key = India
Key = Netherlands
Key = Russia

```

**例 2:**

```cs
// C# code to get the keys
// in the SortedDictionary
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
        Console.WriteLine("Total key/value pairs"
            + " in myDict are : " + myDict.Count);

        // To get the keys alone,
        // use the Keys property.
        SortedDictionary<int, int>.KeyCollection keyColl = 
                                              myDict.Keys;

        // The elements of the KeyCollection
        // are strongly typed with the type
        // that was specified for dictionary
        // keys
        foreach(int s in keyColl)
        {
            Console.WriteLine("Key = {0}", s);
        }
    }
}
```

**Output:**

```cs
Total key/value pairs in myDict are : 4
Key = 1
Key = 3
Key = 4
Key = 9

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . sorted dictionary-2 . keys？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sorteddictionary-2.keys?view=netframework-4.7.2)