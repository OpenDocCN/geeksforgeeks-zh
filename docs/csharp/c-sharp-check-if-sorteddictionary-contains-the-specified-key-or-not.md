# C# |检查 SortedDictionary 是否包含指定的键

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-sorted dictionary-contains-the-specified-key-or-not/](https://www.geeksforgeeks.org/c-sharp-check-if-sorteddictionary-contains-the-specified-key-or-not/)

***排序字典< TKey，TValue >。ContainsKey(TKey)方法*** 用于检查 SortedDictionary 是否包含具有指定键的元素。

**语法:**

```cs
public bool ContainsKey (TKey key);
```

这里*键*是位于排序字典中的键。

**返回值:**如果字典中包含具有指定键的元素，该方法将返回 *true* ，否则返回 *false* 。

**异常:**如果*键*为空，该方法将给出*参数异常*。

以下是说明上述方法使用的程序:

**例 1:**

```cs
// C# code to check if a key is
// present or not in a SortedDictionary.
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Create a new dictionary of
        // strings, with string keys.
        SortedDictionary<int, string> myDict = 
          new SortedDictionary<int, string>();

        // Adding key/value pairs in myDict
        myDict.Add(1, "C");
        myDict.Add(2, "C++");
        myDict.Add(3, "Java");
        myDict.Add(4, "Python");
        myDict.Add(5, "C#");
        myDict.Add(6, "HTML");

        // Checking for Key 4
        if (myDict.ContainsKey(4))
            Console.WriteLine("Key : 4 is present");

        else
            Console.WriteLine("Key : 4 is absent");
    }
}
```

**Output:**

```cs
Key : 4 is present

```

**例 2:**

```cs
// C# code to check if a key is
// present or not in a SortedDictionary.
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

        // Checking for Key "USA"
        if (myDict.ContainsKey("USA"))
            Console.WriteLine("Key : USA is present");

        else
            Console.WriteLine("Key : USA is absent");
    }
}
```

**Output:**

```cs
Key : USA is absent

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . sorted dictionary-2 . contains key？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sorteddictionary-2.containskey?view=netframework-4.7.2)