# C# |获取或设置 StringDictionary

中与指定键关联的值

> 原文:[https://www . geesforgeks . org/c-sharp-get-or-set-the-value-associated-in-specified-key-stringdictionary/](https://www.geeksforgeeks.org/c-sharp-get-or-set-the-value-associated-with-the-specified-key-in-stringdictionary/)

**StringDictionary** 是一个专门的集合。在*T3 系统中可以找到。收藏.专门命名空间*。它只允许字符串键和字符串值。它存在性能问题。它实现了一个哈希表，其中**键**和**值**被强类型化为字符串而不是对象。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to get or set the value
// associated with the specified key
// in StringDictionary
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
        myDict.Add("G", "GeeksforGeeks");
        myDict.Add("C", "Coding");
        myDict.Add("DS", "Data Structures");
        myDict.Add("N", "Noida");
        myDict.Add("GC", "Geeks Classes");

        // Displaying the keys and values
        // in StringDictionary
        foreach(DictionaryEntry de in myDict)
        {
            Console.WriteLine(de.Key + " " + de.Value);
        }

        // To get the value corresponding to key "C"
        Console.WriteLine(myDict["C"]);

        // Changing the value corresponding to key "C"
        myDict["C"] = "C++";

        // To get the value corresponding to key "C"
        Console.WriteLine(myDict["C"]);

        // To get the value corresponding to key "N"
        Console.WriteLine(myDict["N"]);

        // Changing the value corresponding to key "N"
        myDict["N"] = "North";

        // To get the value corresponding to key "N"
        Console.WriteLine(myDict["N"]);

        // Displaying the keys and values
        // in StringDictionary
        foreach(DictionaryEntry de in myDict)
        {
            Console.WriteLine(de.Key + " " + de.Value);
        }
    }
}
```

**输出:**

```cs
gc Geeks Classes
c Coding
n Noida
ds Data Structures
g GeeksforGeeks
Coding
C++
Noida
North
c C++
g GeeksforGeeks
gc Geeks Classes
ds Data Structures
n North

```