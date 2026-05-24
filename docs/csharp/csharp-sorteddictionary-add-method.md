# C# | SortedDictionary。添加()方法

> 原文:[https://www . geeksforgeeks . org/cs harp-sorted dictionary-add-method/](https://www.geeksforgeeks.org/csharp-sorteddictionary-add-method/)

这用于将指定的键和值添加到已排序的字典中。元素根据 TKey 进行排序。

**语法:**

```cs
public void Add (TKey key, TValue value);

```

**参数:**

> *键:*是要添加的元素的键。
> *值:*是元素添加的值。对于引用类型，该值可以为 null。

**异常:**

*   *ArgumentNullException :* 如果密钥为空。
*   *ArgumentException :* 如果字典中已经存在具有相同键的元素。

以下是说明使用**字典< TKey，TValue >的程序。添加()方法:**

**例 1:**

```cs
// C# code to add the specified key
// and value into the SortedDictionary
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

        // To get count of key/value
        // pairs in myDict
        Console.WriteLine("Total key/value pairs in"
                 + " myDict are : " + myDict.Count);

        // Displaying the key/value
        // pairs in myDict
        Console.WriteLine("The key/value pairs"
                          + " in myDict are : ");

        foreach(KeyValuePair<string, string> kvp in myDict)
        {
            Console.WriteLine("Key = {0}, Value = {1}",
                              kvp.Key, kvp.Value);
        }
    }
}
```

**Output:**

```cs
Total key/value pairs in myDict are : 6
The key/value pairs in myDict are : 
Key = Australia, Value = Canberra
Key = Belgium, Value = Brussels
Key = China, Value = Beijing
Key = India, Value = New Delhi
Key = Netherlands, Value = Amsterdam
Key = Russia, Value = Moscow

```

**例 2:**

```cs
// C# code to add the specified key
// and value into the SortedDictionary
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

        // The Add method throws an
        // exception if the new key is
        // already in the dictionary.
        try {

            myDict.Add("Russia", "Moscow");
        }

        catch (ArgumentException) {

            Console.WriteLine("An element with Key "
                  + "= \"Russia\" already exists.");
        }
    }
}
```

**Output:**

```cs
An element with Key = "Russia" already exists.

```

**注:**

*   键不能为空，但值可以为空。如果值类型 TValue 是引用类型。
*   这个方法是一个 O(log n)操作，其中 n 是 SortedDictionary 中元素的计数。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . sorted dictionary-2 . add？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sorteddictionary-2.add?view=netframework-4.7.2)