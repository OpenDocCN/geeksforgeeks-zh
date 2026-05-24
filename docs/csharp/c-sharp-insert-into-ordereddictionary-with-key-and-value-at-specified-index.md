# C# |插入到有序字典中，键和值在指定的索引处

> 原文:[https://www . geeksforgeeks . org/c-sharp-insert-in-ordered dictionary-按指定索引键和值/](https://www.geeksforgeeks.org/c-sharp-insert-into-ordereddictionary-with-key-and-value-at-specified-index/)

**OrderedDictionary。Insert(Int32，Object，Object)** 方法用于在 OrderedDictionary 集合中插入一个新条目，该条目在指定索引处具有指定的键和值。

**语法:**

```cs
public void Insert (int index, object key, object value);

```

**参数:**

> **索引:**是元素应该插入的从零开始的索引。
> **键:**是词条添加的键。
> **值:**是要添加的条目的值。该值可以为空。

**异常:**

*   **NotSupportedException :** 如果 OrderedDictionary 集合是只读的。
*   **argumentoutofrangerexception:**如果索引超出范围。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to insert entry into
// OrderedDictionary with key and
// value at the specified index
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

        // Inserting entry into OrderedDictionary
        // with key and value at the specified index
        myDict.Insert(2, "Geeks", "Noida");

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
Number of elements are : 6
key1 -- value1
key2 -- value2
Geeks -- Noida
key3 -- value3
key4 -- value4
key5 -- value5

```

**例 2:**

```cs
// C# code to insert entry into
// OrderedDictionary with key and
// value at the specified index
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

        // Inserting entry into OrderedDictionary
        // with key and value at the specified index
        // This should raise "ArgumentOutOfRangeException"
        // as index is out of range
        myDict.Insert(10, "E", "Elephant");

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
> 系统。ArgumentOutOfRangeException:指定的参数超出有效值范围。
> 参数名称:索引

**注:**

*   如果索引参数等于 OrderedDictionary 集合中的条目数，则键和值参数将附加到集合的末尾。
*   插入点之后的条目向下移动以容纳新条目，并且移动条目的索引也会更新。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . ordered dictionary . insert？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.ordereddictionary.insert?view=netframework-4.7.2)