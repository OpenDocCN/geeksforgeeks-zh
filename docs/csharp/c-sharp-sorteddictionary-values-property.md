# C# | SortedDictionary。价值属性

> 原文:[https://www . geeksforgeeks . org/c-sharp-sorted dictionary-values-property/](https://www.geeksforgeeks.org/c-sharp-sorteddictionary-values-property/)

此属性用于获取包含 SortedDictionary 中的值的集合。

**语法:**

```cs
public System.Collections.Generic.SortedDictionary<TKey,TValue>.ValueCollection Values { get; }
```

**返回值:**它返回一个包含 SortedDictionary 中的值的集合。

下面是说明上述属性使用的程序:

**例 1:**

```cs
// C# code to get the values
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

        // To get the values alone,
        // use the Values property.
        SortedDictionary<string, string>.ValueCollection valColl = 
                                                     myDict.Values;

        // The elements of the ValueCollection
        // are strongly typed with the type
        // that was specified for dictionary
        // values
        foreach(string s in valColl)
        {
            Console.WriteLine("Value = {0}", s);
        }
    }
}
```

**Output:**

```cs
Total key/value pairs in myDict are : 6
Value = Canberra
Value = Brussels
Value = Beijing
Value = New Delhi
Value = Amsterdam
Value = Moscow

```

**例 2:**

```cs
// C# code to get the values
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

        // To get the values alone,
        // use the Values property.
        SortedDictionary<int, int>.ValueCollection valColl = 
                                               myDict.Values;

        // The elements of the ValueCollection
        // are strongly typed with the type
        // that was specified for dictionary
        // values
        foreach(int s in valColl)
        {
            Console.WriteLine("Value = {0}", s);
        }
    }
}
```

**Output:**

```cs
Total key/value pairs in myDict are : 4
Value = 7
Value = 4
Value = 7
Value = 8

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . sorted dictionary-2 . values？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sorteddictionary-2.values?view=netframework-4.7.2)