# C# |字典。ContainsKey()方法

> 原文:[https://www . geesforgeks . org/c-sharp-dictionary-contains key-method/](https://www.geeksforgeeks.org/c-sharp-dictionary-containskey-method/)

该方法用于检查字典<tkey>是否包含指定的键。</tkey>

**语法:**

```cs
public bool ContainsKey (TKey key);

```

这里*键*是要在字典中定位的键。

**返回值:**如果字典中包含具有指定键的元素，该方法将返回 *true* ，否则返回 *false* 。

**异常:**如果密钥为空，该方法将给出 *ArgumentNullException* 。

以下是说明使用**字典< TKey，TValue >的程序。ContainsKey()方法**:

**例 1:**

```cs
// C# code to check if a key is 
// present or not in a Dictionary.
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

        // Checking for Key "India"
        if (myDict.ContainsKey("India"))
            Console.WriteLine("Key : India is present");

        else
            Console.WriteLine("Key : India is absent");
    }
}
```

**Output:**

```cs
Key : India is present

```

**例 2:**

```cs
// C# code to check if a key is 
// present or not in a Dictionary.
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

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . dictionary-2 . contains key？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.dictionary-2.containskey?view=netframework-4.7.2)