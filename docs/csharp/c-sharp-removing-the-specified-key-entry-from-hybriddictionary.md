# C# |从混合字典中删除指定的关键字条目

> 原文:[https://www . geesforgeks . org/c-sharp-从混合字典中删除指定的关键字条目/](https://www.geeksforgeeks.org/c-sharp-removing-the-specified-key-entry-from-hybriddictionary/)

**杂交词典。移除(对象)**方法用于从混合字典中移除具有指定关键字的条目。

**语法:**

```cs
public void Remove (object key);

```

在这里， ***键*** 是要移除的条目的键。

**异常:**此方法抛出***ArgumentNullException***如果关键是 ***空*** 。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to remove the entry
// with the specified key from
// the HybridDictionary.
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

        // Removing the entry with the
        // specified key from the HybridDictionary.
        myDict.Remove("C");

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

**输出:**

```cs
Number of key/value pairs in myDict are : 6
The key/value pairs in myDict are : 
A --> Apple
B --> Banana
C --> Cat
D --> Dog
E --> Elephant
F --> Fish
Number of key/value pairs in myDict are : 5
The key/value pairs in myDict are : 
A --> Apple
B --> Banana
D --> Dog
E --> Elephant
F --> Fish

```

**例 2:**

```cs
// C# code to remove the entry
// with the specified key from
// the HybridDictionary.
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

        // Removing the entry with the
        // specified key from the HybridDictionary.
        // This should raise "ArgumentNullException"
        // as the key is "null"
        myDict.Remove(null);

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

**运行时错误:**

> 未处理异常:
> 系统。ArgumentNullException:键不能为空。
> 参数名称:键

**注:**

*   如果**混合字典**不包含具有指定键的元素，则混合字典保持不变。不会引发异常。
*   如果集合已经存储在**哈希表**中，并且元素数量低于列表字典的最佳大小，则集合将保留在哈希表中，以避免将元素从哈希表复制回列表字典的开销。
*   这个方法是一个 **O(1)** 运算。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . hybrid dictionary . remove？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.hybriddictionary.remove?view=netframework-4.7.2)