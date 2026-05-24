# C# |从列表字典中删除所有条目

> 原文:[https://www . geesforgeks . org/c-sharp-从列表词典中删除所有条目/](https://www.geeksforgeeks.org/c-sharp-remove-all-entries-from-the-listdictionary/)

**列表词典。清除**方法用于从列表字典中删除所有条目。

**语法:**

```cs
public void Clear ();

```

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to remove all entries
// from the ListDictionary
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a ListDictionary named myDict
        ListDictionary myDict = new ListDictionary();

        // Adding key/value pairs in myDict
        myDict.Add("Australia", "Canberra");
        myDict.Add("Belgium", "Brussels");
        myDict.Add("Netherlands", "Amsterdam");
        myDict.Add("China", "Beijing");
        myDict.Add("Russia", "Moscow");
        myDict.Add("India", "New Delhi");

        // To get count of key/value pairs in myDict
        Console.WriteLine("Total key/value pairs in myDict are : " 
                                                  + myDict.Count);

        // Displaying the key/value pairs in myDict
        Console.WriteLine("The key/value pairs in myDict are : ");

        foreach(DictionaryEntry de in myDict)
        {
            Console.WriteLine(de.Key + " " + de.Value);
        }

        // Removing all entries from the ListDictionary
        myDict.Clear();

        // To get count of key/value pairs in myDict
        Console.WriteLine("Total key/value pairs in myDict are : "
                                                  + myDict.Count);

        // Displaying the key/value pairs in myDict
        Console.WriteLine("The key/value pairs in myDict are : ");

        foreach(DictionaryEntry de in myDict)
        {
            Console.WriteLine(de.Key + " " + de.Value);
        }
    }
}
```

**输出:**

```cs
Total key/value pairs in myDict are : 6
The key/value pairs in myDict are : 
Australia Canberra
Belgium Brussels
Netherlands Amsterdam
China Beijing
Russia Moscow
India New Delhi
Total key/value pairs in myDict are : 0
The key/value pairs in myDict are :

```