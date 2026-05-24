# C# |用指定的键和值在 OrderedDictionary 中插入一个新条目

> 原文:[https://www . geesforgeks . org/c-sharp-insert-a-new-entry-in-ordered dictionary-with-specified-key-and-value/](https://www.geeksforgeeks.org/c-sharp-insert-a-new-entry-in-ordereddictionary-with-specified-key-and-value/)

**OrderedDictionary。Insert(Int32，Object，Object)方法**用于在指定索引处用指定的键和值向**[OrderedDictionary](https://www.geeksforgeeks.org/c-ordereddictionary-class/)**集合插入一个新条目。

**语法:**

```cs
public void Insert (int index, object key, object value);
```

**参数:**

> **指数:**是*系统类型的零基指数。Int32* 元素应该插入的位置。
> 
> **键:**是要添加的条目的键。
> 
> **值:**是要添加的条目的值。该值可以是*空值*。

**异常:**

*   **argumentoutofrangerexception:**如果*指数*超出范围。
*   **NotSupportedException:** 如果集合是只读的。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to add a new entry into the
// OrderedDictionary collection with
// the specified key and value at the
// specified index.
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

        Console.WriteLine("Before Updation: ");

        // Displaying the key/value pairs in myDict
        foreach(DictionaryEntry de in myDict)
            Console.WriteLine(de.Key + " --> " + de.Value);

        // using Insert(Int32, Object, Object) Method
        // to add a new entry at index 5
        myDict.Insert(5, "key6", "value6");

        Console.WriteLine("\nAfter Updation: ");

        // Displaying the key/value pairs in myDict
        foreach(DictionaryEntry de in myDict)
            Console.WriteLine(de.Key + " --> " + de.Value);
    }
}
```

**输出:**

```cs
Before Updation: 
key1 --> value1
key2 --> value2
key3 --> value3
key4 --> value4
key5 --> value5

After Updation: 
key1 --> value1
key2 --> value2
key3 --> value3
key4 --> value4
key5 --> value5
key6 --> value6

```

**例 2:**

```cs
// C# code to add a new entry into the
// OrderedDictionary collection with
// the specified key and value at the
// specified index.
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
        myDict.Add("1", "C");
        myDict.Add("2", "C++");
        myDict.Add("3", "Java");
        myDict.Add("4", "Python");
        myDict.Add("5", "C#");

        Console.WriteLine("Before Updation: ");

        // Displaying the key/value pairs in myDict
        foreach(DictionaryEntry de in myDict)
            Console.WriteLine(de.Key + " --> " + de.Value);

        // using Insert(Int32, Object, Object) Method
        // this will give error as index is out of range
        // here indexing is zero-based
        myDict.Insert(6, "6", "HTML");

        Console.WriteLine("\nAfter Updation: ");

        // Displaying the key/value pairs in myDict
        foreach(DictionaryEntry de in myDict)
            Console.WriteLine(de.Key + " --> " + de.Value);
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentOutOfRangeException:指定的参数超出有效值范围。
> 参数名称:索引

**注:**

*   如果索引参数等于 OrderedDictionary 集合中的条目数，则键和值参数将被追加到集合的末尾。
*   插入点之后的条目向下移动以容纳新条目，并且移动条目的索引也会更新。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . ordered dictionary . insert？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.ordereddictionary.insert?view=netframework-4.7.2)