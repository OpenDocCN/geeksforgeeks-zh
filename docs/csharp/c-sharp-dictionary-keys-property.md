# C# |字典。密钥属性

> 原文:[https://www . geesforgeks . org/c-sharp-dictionary-keys-property/](https://www.geeksforgeeks.org/c-sharp-dictionary-keys-property/)

此属性用于获取包含字典中的键的集合。

**语法:**

> 公共系统。集合。类属。词典<tkey tvalue="">。KeyCollection Keys { get}</tkey>

**返回值:**返回包含字典中关键字的集合。

以下是说明上述属性使用的程序:

**例 1:**

```cs
// C# code to get the keys
// in the Dictionary
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

        // To get count of key/value pairs in myDict
        Console.WriteLine("Total key/value pairs"+
              " in myDict are : " + myDict.Count);

        // To get the keys alone, 
        // use the Keys property.
        Dictionary<string, string>.KeyCollection keyColl = 
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
Key = Netherlands
Key = China
Key = Russia
Key = India

```

**例 2:**

```cs
// C# code to get the keys in the Dictionary
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

        // To get the keys alone, 
        // use the Keys property.
        Dictionary<int, int>.KeyCollection keyColl = 
                                       myDict.Keys;

        // The elements of the KeyCollection
        // are strongly typed with the type 
        // that was specified for dictionary keys.
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
Key = 9
Key = 3
Key = 4
Key = 1

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . dictionary-2 . keys？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.dictionary-2.keys?view=netframework-4.7.2)