# C# |从字符串中删除所有条目

> 原文:[https://www . geeksforgeeks . org/c-sharp-remove-all-entries-from-stringdictionary/](https://www.geeksforgeeks.org/c-sharp-removing-all-entries-from-the-stringdictionary/)

**StringDictionary。清除**方法用于**从字符串中移除所有条目**。

**语法:**

```cs
public virtual void Clear ();

```

**异常:**如果*字符串*为只读，此方法将给出 *NotSupportedException* 。

**示例:**

```cs
// C# code to remove all entries
// from the StringDictionary
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a StringDictionary named myDict
        StringDictionary myDict = new StringDictionary();

        // Adding key and value into the StringDictionary
        myDict.Add("A", "Apple");
        myDict.Add("B", "Banana");
        myDict.Add("C", "Cat");
        myDict.Add("D", "Dog");
        myDict.Add("E", "Elephant");
        myDict.Add("F", "Fish");

        // Displaying the keys and values in StringDictionary
        Console.WriteLine("The number of key/value pairs are : " + myDict.Count);

        foreach(DictionaryEntry dic in myDict)
        {
            Console.WriteLine(dic.Key + " " + dic.Value);
        }

        // Removing all entries from the StringDictionary
        myDict.Clear();

        // Displaying the keys and values in StringDictionary
        Console.WriteLine("The number of key/value pairs are : " + myDict.Count);

        foreach(DictionaryEntry dic in myDict)
        {
            Console.WriteLine(dic.Key + " " + dic.Value);
        }
    }
}
```

**Output:**

```cs
The number of key/value pairs are : 6
b Banana
c Cat
a Apple
f Fish
d Dog
e Elephant
The number of key/value pairs are : 0

```

**注:**此方法为 O(n)运算，其中 n 为 Count。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . string dictionary . clear？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringdictionary.clear?view=netframework-4.7.2)