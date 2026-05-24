# C# |字典。价值属性

> 原文:[https://www . geesforgeks . org/c-sharp-dictionary-values-property/](https://www.geeksforgeeks.org/c-sharp-dictionary-values-property/)

该属性用于获取包含字典<tkey>中值的集合。</tkey>

**语法:**

> 公共系统。集合。类属。词典<tkey tvalue="">。KeyCollection 值{ get}</tkey>

**返回值:**该属性返回包含字典中值的集合。

以下是说明使用**字典< TKey，TValue >的程序。值**属性:

**例 1:**

```cs
// C# code to get the Values
// in the Dictionary
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Create a new dictionary
        // of strings, with string keys.
        Dictionary<string, string> myDict = 
           new Dictionary<string, string>();

        // Adding key/value pairs in myDict
        myDict.Add("Australia", "Canberra");
        myDict.Add("Belgium", "Brussels");
        myDict.Add("Netherlands", "Amsterdam");
        myDict.Add("China", "Beijing");
        myDict.Add("Russia", "Moscow");
        myDict.Add("India", "New Delhi");

        // To get count of key/value pairs in myDict
        Console.WriteLine("Total key/value pairs"+
               " in myDict are : " + myDict.Count);

        // To get the values alone,
        // use the Values property.
        Dictionary<string, string>.ValueCollection valueColl = 
                                                myDict.Values;

        // The elements of the ValueCollection
        // are strongly typed with the type 
        // that was specified for dictionary values.
        foreach(string s in valueColl)
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
Value = Amsterdam
Value = Beijing
Value = Moscow
Value = New Delhi

```

**例 2:**

```cs
// C# code to get the values
// in the Dictionary
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Create a new dictionary of
        // strings, with string keys.
        Dictionary<int, int> myDict = 
           new Dictionary<int, int>();

        // Adding key/value pairs in myDict
        myDict.Add(9, 8);
        myDict.Add(3, 4);
        myDict.Add(4, 7);
        myDict.Add(1, 7);

        // To get count of key/value pairs in myDict
        Console.WriteLine("Total key/value pairs "+
                "in myDict are : " + myDict.Count);

        // To get the values alone, 
        // use the Values property.
        Dictionary<int, int>.ValueCollection valueColl =  
                                           myDict.Values;

        // The elements of the ValueCollection
        // are strongly typed with the type 
        // that was specified for dictionary values.
        foreach(int s in valueColl)
        {
            Console.WriteLine("Values = {0}", s);
        }
    }
}
```

**Output:**

```cs
Total key/value pairs in myDict are : 4
Values = 8
Values = 4
Values = 7
Values = 7

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . dictionary-2 . values？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.dictionary-2.values?view=netframework-4.7.2)