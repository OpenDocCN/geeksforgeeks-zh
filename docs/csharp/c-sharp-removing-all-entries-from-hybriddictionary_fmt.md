# C# | 从混合字典中删除所有条目

> 原文: [https://www.geeksforgeeks.org/c-sharp-removing-all-entries-from-hybriddictionary/](https://www.geeksforgeeks.org/c-sharp-removing-all-entries-from-hybriddictionary/)

`HybridDictionary.Clear` 方法用于从混合字典中移除所有条目。

## 语法

```cs
public void Clear ();
```

下面给出了一些例子，以便更好地理解实现：

## 例 1

```cs
// C# code to removes all entries
// from the HybridDictionary.
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

// Driver code
    public static void Main()
    {

// Creating a HybridDictionary named myDict
        HybridDictionary myDict = new HybridDictionary();

// Adding key/value pairs in myDict
        myDict.Add("A", "Apple");
        myDict.Add("B", "Banana");
        myDict.Add("C", "Cat");
        myDict.Add("D", "Dog");
        myDict.Add("E", "Elephant");
        myDict.Add("F", "Fish");

// Displaying the number of key/value
        // pairs in HybridDictionary myDict
        Console.WriteLine("Number of key/value pairs in myDict are : " 
                                          + myDict.Count);

// Displaying the key/value pairs in myDict
        Console.WriteLine("The key/value pairs in myDict are : ");

foreach(DictionaryEntry de in myDict)
        {
            Console.WriteLine(de.Key + " --> " + de.Value);
        }

// Removing all entries from myDict
        myDict.Clear();

// Displaying the number of key/value
        // pairs in HybridDictionary myDict
        Console.WriteLine("Number of key/value pairs in myDict are : " 
                                           + myDict.Count);

// Displaying the key/value pairs in myDict
        Console.WriteLine("The key/value pairs in myDict are : ");

foreach(DictionaryEntry de in myDict)
        {
            Console.WriteLine(de.Key + " --> " + de.Value);
        }
    }
}
```

## 输出

```cs
Number of key/value pairs in myDict are : 6
The key/value pairs in myDict are : 
A --> Apple
B --> Banana
C --> Cat
D --> Dog
E --> Elephant
F --> Fish
Number of key/value pairs in myDict are : 0
The key/value pairs in myDict are :
```

## 例 2

```cs
// C# code to removes all entries
// from the HybridDictionary.
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

// Driver code
    public static void Main()
    {

// Creating a HybridDictionary named myDict
        HybridDictionary myDict = new HybridDictionary();

// Adding key/value pairs in myDict
        myDict.Add("I", "first");
        myDict.Add("II", "second");
        myDict.Add("III", "third");
        myDict.Add("IV", "fourth");
        myDict.Add("V", "fifth");

// Displaying the number of key/value
        // pairs in HybridDictionary myDict
        Console.WriteLine("Number of key/value pairs in myDict are : " 
                                          + myDict.Count);

// Displaying the key/value pairs in myDict
        Console.WriteLine("The key/value pairs in myDict are : ");

foreach(DictionaryEntry de in myDict)
        {
            Console.WriteLine(de.Key + " --> " + de.Value);
        }

// Removing all entries from myDict
        myDict.Clear();

// Displaying the number of key/value
        // pairs in HybridDictionary myDict
        Console.WriteLine("Number of key/value pairs in myDict are : " 
                                           + myDict.Count);

// Displaying the key/value pairs in myDict
        Console.WriteLine("The key/value pairs in myDict are : ");

foreach(DictionaryEntry de in myDict)
        {
            Console.WriteLine(de.Key + " --> " + de.Value);
        }
    }
}
```

## 输出

```cs
Number of key/value pairs in myDict are : 5
The key/value pairs in myDict are : 
I --> first
II --> second
III --> third
IV --> fourth
V --> fifth
Number of key/value pairs in myDict are : 0
The key/value pairs in myDict are :
```

## 注

*   `Count` 设置为零，集合元素对其他对象的引用也会被释放。
*   如果集合已经存储在 `Hashtable` 中，该集合将保留在 `Hashtable` 中。
*   这个方法是一个 `O(n)` 运算，其中 `n` 是 `Count`。

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.hybriddictionary.clear?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.hybriddictionary.clear?view=netframework-4.7.2)