# C# |从 OrderedDictionary

中删除带有指定键的条目

> 原文:[https://www . geesforgeks . org/c-sharp-remove-entry-with-specified-key-from-ordered dictionary/](https://www.geeksforgeeks.org/c-sharp-remove-entry-with-specified-key-from-ordereddictionary/)

**OrderedDictionary。Remove(Object)** 方法用于从 OrderedDictionary 集合中移除具有指定键的条目。

**语法:**

```cs
public void Remove (object key);

```

在这里， ***键*** 是要移除的条目的键。

**异常:**

*   **NotSupportedException :** 如果 OrderedDictionary 集合是只读的。
*   **ArgumentNullException :** 如果密钥为空。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to remove the entry
// with the specified key from
// the OrderedDictionary
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver method
    public static void Main()
    {

        // Creating a orderedDictionary named myDict
        OrderedDictionary myDict = new OrderedDictionary();

        // Adding key and value in myDict
        myDict.Add("key1", "value1");
        myDict.Add("key2", "value2");
        myDict.Add("key3", "value3");
        myDict.Add("key4", "value4");
        myDict.Add("key5", "value5");

        // Displaying the number of element initially
        Console.WriteLine("Number of elements are : " 
                                     + myDict.Count);

        // Displaying the elements in myDict
        foreach(DictionaryEntry de in myDict)
            Console.WriteLine(de.Key + " -- " + de.Value);

        // Removing the entry with the specified
        // key from the OrderedDictionary
        myDict.Remove("key2");

        // Displaying the number of element initially
        Console.WriteLine("Number of elements are : " 
                                     + myDict.Count);

        // Displaying the elements in myDict
        foreach(DictionaryEntry de in myDict)
            Console.WriteLine(de.Key + " -- " + de.Value);
    }
}
```

**输出:**

```cs
Number of elements are : 5
key1 -- value1
key2 -- value2
key3 -- value3
key4 -- value4
key5 -- value5
Number of elements are : 4
key1 -- value1
key3 -- value3
key4 -- value4
key5 -- value5

```

**例 2:**

```cs
// C# code to remove the entry
// with the specified key from
// the OrderedDictionary
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver method
    public static void Main()
    {

        // Creating a orderedDictionary named myDict
        OrderedDictionary myDict = new OrderedDictionary();

        // Adding key and value in myDict
        myDict.Add("A", "Apple");
        myDict.Add("B", "Banana");
        myDict.Add("C", "Cat");
        myDict.Add("D", "Dog");

        // Displaying the number of element initially
        Console.WriteLine("Number of elements are : " 
                                     + myDict.Count);

        // Displaying the elements in myDict
        foreach(DictionaryEntry de in myDict)
            Console.WriteLine(de.Key + " -- " + de.Value);

        // Removing the entry with the specified
        // key from the OrderedDictionary
        // This should raise "ArgumentNullException"
        // as the key is null
        myDict.Remove(null);

        // Displaying the number of element initially
        Console.WriteLine("Number of elements are : " 
                                     + myDict.Count);

        // Displaying the elements in myDict
        foreach(DictionaryEntry de in myDict)
            Console.WriteLine(de.Key + " -- " + de.Value);
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentNullException:值不能为空。
> 参数名称:键

**注:**

*   被移除的条目之后的条目向上移动以占据空出的位置，并且被移动的条目的索引也被更新。
*   如果 OrderedDictionary 集合不包含具有指定键的条目，OrderedDictionary 将保持不变，并且不会引发异常。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . ordered dictionary . remove？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.ordereddictionary.remove?view=netframework-4.7.2)