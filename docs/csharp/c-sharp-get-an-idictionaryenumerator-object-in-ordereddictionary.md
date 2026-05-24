# C# |获取有序字典中的 IDictionaryEnumerator 对象

> 原文:[https://www . geesforgeks . org/c-sharp-get-an-idictionarylumerator-object-in-ordered dictionary/](https://www.geeksforgeeks.org/c-sharp-get-an-idictionaryenumerator-object-in-ordereddictionary/)

**OrderedDictionary。GetEnumerator** 方法返回一个 [IDictionaryEnumerator](https://docs.microsoft.com/en-us/dotnet/api/system.collections.idictionaryenumerator?view=netframework-4.7.2) 对象，该对象遍历 OrderedDictionary 集合。

**语法:**

```cs
public virtual System.Collections.IDictionaryEnumerator GetEnumerator ();

```

**返回值:**有序字典集合的一个[字典枚举器](https://docs.microsoft.com/en-us/dotnet/api/system.collections.idictionaryenumerator?view=netframework-4.7.2)对象。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to get an IDictionaryEnumerator
// object that iterates through the
// OrderedDictionary collection.
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

        // To Get an IDictionaryEnumerator object
        // that iterates through the OrderedDictionary
        // collection.
        IDictionaryEnumerator myEnumerator = myDict.GetEnumerator();

        while (myEnumerator.MoveNext()) {
            Console.WriteLine(myEnumerator.Key + " --> " 
                                  + myEnumerator.Value);
        }
    }
}
```

**输出:**

```cs
key1 --> value1
key2 --> value2
key3 --> value3
key4 --> value4
key5 --> value5

```

**例 2:**

```cs
// C# code to get an IDictionaryEnumerator
// object that iterates through the
// OrderedDictionary collection.
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

        // To Get an IDictionaryEnumerator object
        // that iterates through the OrderedDictionary
        // collection.
        IDictionaryEnumerator myEnumerator = myDict.GetEnumerator();

        while (myEnumerator.MoveNext()) {
            Console.WriteLine(myEnumerator.Key + " --> " 
                                 + myEnumerator.Value);
        }
    }
}
```

**输出:**

```cs
A --> Apple
B --> Banana
C --> Cat
D --> Dog

```

**注:**

*   枚举数可用于读取集合中的数据，但不能用于修改基础集合。
*   最初，枚举数位于集合中的第一个元素之前。
*   这个方法是一个 O(1)运算。
*   只要集合保持不变，枚举数就保持有效。如果对集合进行了更改，例如添加、修改或删除元素，枚举数将无法恢复地失效，并且其行为未定义。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . ordereddictionary . getenumerator？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.ordereddictionary.getenumerator?view=netframework-4.7.2)