# C# |获取一个包含列表字典

中的值的集合

> 原文:[https://www . geesforgeks . org/c-sharp-get-an-I collection-contain-the-values-in-list dictionary/](https://www.geeksforgeeks.org/c-sharp-get-an-icollection-containing-the-values-in-listdictionary/)

**列表词典。Values** 属性用于获取一个包含列表字典中的值的 ICollection。

**语法:**

```cs
public System.Collections.ICollection Values { get; }

```

**返回值:**它返回一个包含列表字典中的值的[集合](https://docs.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=netframework-4.7.2)。

以下是说明**列表词典使用的程序。值**属性:

**例 1:**

```cs
// C# code to get an ICollection
// containing the values in the ListDictionary
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a ListDictionary named myDict
        ListDictionary myDict = new ListDictionary();

        myDict.Add("Australia", "Canberra");
        myDict.Add("Belgium", "Brussels");
        myDict.Add("Netherlands", "Amsterdam");
        myDict.Add("China", "Beijing");
        myDict.Add("Russia", "Moscow");
        myDict.Add("India", "New Delhi");

        // Get an ICollection containing
        // the values in the ListDictionary
        ICollection ic = myDict.Values;

        // Displaying the values in ICollection ic
        foreach(String str in ic)
        {
            Console.WriteLine(str);
        }
    }
}
```

**Output:**

```cs
Canberra
Brussels
Amsterdam
Beijing
Moscow
New Delhi

```

**例 2 :**

```cs
// C# code to get an ICollection
// containing the values in the ListDictionary
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a ListDictionary named myDict
        ListDictionary myDict = new ListDictionary();

        myDict.Add("I", "first");
        myDict.Add("II", "second");
        myDict.Add("III", "third");
        myDict.Add("IV", "fourth");
        myDict.Add("V", "fifth");

        // Get an ICollection containing
        // the values in the ListDictionary
        ICollection ic = myDict.Values;

        // Displaying the values in ICollection ic
        foreach(String str in ic)
        {
            Console.WriteLine(str);
        }
    }
}
```

**Output:**

```cs
first
second
third
fourth
fifth

```

**注:**

*   icocollection 中值的顺序未指定，但它与 keys 方法返回的 icocollection 中关联键的顺序相同。
*   返回的 ICollection 不是静态副本。取而代之的是，ICollection 引用回原始列表字典中的值。因此，对列表词典的更改将继续反映在 ICollection 中。
*   检索该属性的值是一个 O(1)操作。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . list dictionary . values？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.listdictionary.values?view=netframework-4.7.2)