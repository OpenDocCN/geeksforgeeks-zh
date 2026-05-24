# C# | SortedDictionary。ContainsValue()方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-sorted dictionary-contains value-method/](https://www.geeksforgeeks.org/c-sharp-sorteddictionary-containsvalue-method/)

该方法用于检查**排序字典< TKey，t value>T1 是否包含指定值的元素。**

**语法:**

```cs
public bool ContainsValue (TValue value);

```

这里，*值*是要在排序字典中定位的值。参考类型的值可以是*空值*。

**返回值:**如果 SortedDictionary 包含具有指定值的元素，则该方法返回 *true* ，否则返回 *false* 。

以下是说明使用**排序字典< TKey，TValue >的程序。ContainsValue()方法**:

**例 1:**

```cs
// C# code to check if a value
// is present or not in a 
// SortedDictionary.
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

        // Checking the value "India" but
        // here "India" is the key
        if (myDict.ContainsValue("India"))
            Console.WriteLine("Value : India is present.");

        else
            Console.WriteLine("Value : India is not present.");
    }
}
```

**Output:**

```cs
Value : India is not present.

```

**例 2:**

```cs
// C# code to check if a value
// is present or not in a 
// SortedDictionary.
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

        // Checking for value Moscow
        if (myDict.ContainsValue("Moscow"))
            Console.WriteLine("Value : Moscow is present");

        else
            Console.WriteLine("Value : Moscow is absent");
    }
}
```

**Output:**

```cs
Value : Moscow is present

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . sorted dictionary-2 . contains value？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sorteddictionary-2.containsvalue?view=netframework-4.7.2)