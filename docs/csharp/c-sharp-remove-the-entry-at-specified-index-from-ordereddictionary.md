# C# |从有序字典

中删除指定索引处的条目

> 原文:[https://www . geeksforgeeks . org/c-sharp-从 ordereddictionary 中删除指定索引处的条目/](https://www.geeksforgeeks.org/c-sharp-remove-the-entry-at-specified-index-from-ordereddictionary/)

**OrderedDictionary。RemoveAt(Int32)** 方法用于从 OrderedDictionary 集合中移除指定索引处的条目。

**语法:**

```cs
public void RemoveAt (int index);

```

这里， ***索引*** 是要移除的条目的从零开始的索引。

**异常:**

*   **NotSupportedException :** 如果 OrderedDictionary 集合是只读的。
*   **argumentoutofrangerexception:**如果指数小于零 ***或*** 指数等于或大于 Count。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to remove the entry at
// the specified index from the
// OrderedDictionary
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

        // Removing the entry at the specified
        // index from the OrderedDictionary
        myDict.RemoveAt(3);

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
key2 -- value2
key3 -- value3
key5 -- value5

```

**例 2:**

```cs
// C# code to remove the entry at
// the specified index from the
// OrderedDictionary
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

        // Removing the entry at the specified
        // index from the OrderedDictionary
        // This should raise "ArgumentOutOfRangeException"
        // as index is less than 0
        myDict.RemoveAt(-2);

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

**注意:**被移除条目之后的条目向上移动以占据空出的位置，并且移动的条目的索引也被更新。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . ordered dictionary . remove at？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.ordereddictionary.removeat?view=netframework-4.7.2)