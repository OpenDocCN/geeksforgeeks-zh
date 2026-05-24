# C# |检查 OrderedDictionary 集合是否为只读

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-ordered dictionary-collection-is-read-only/](https://www.geeksforgeeks.org/c-sharp-check-if-ordereddictionary-collection-is-read-only/)

**OrderedDictionary。IsReadOnly** 属性用于获取一个值，该值指示 OrderedDictionary 集合是否为只读。

**语法:**

```cs
public bool IsReadOnly { get; }

```

**返回值:**如果 OrderedDictionary 集合为只读，则该属性返回 ***True*** ，否则返回 ***False*** 。默认为 ***假*** 。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to check if OrderedDictionary
// collection is read-only
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

        // Checking if OrderedDictionary
        // collection is read-only
        Console.WriteLine(myDict.IsReadOnly);
    }
}
```

**输出:**

```cs
False

```

**例 2:**

```cs
// C# code to check if OrderedDictionary
// collection is read-only
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

        // Checking if OrderedDictionary
        // collection is read-only
        // if not, insert a new key in beginning
        // of myDict
        if (!myDict.IsReadOnly)
            myDict.Insert(0, "E", "Elephant");

        // Displaying the elements in myDict
        foreach(DictionaryEntry de in myDict)
            Console.WriteLine(de.Key + " -- " + de.Value);
    }
}
```

**输出:**

```cs
E -- Elephant
A -- Apple
B -- Banana
C -- Cat
D -- Dog

```

**注:**

*   只读集合在创建后不允许添加、移除或修改元素。
*   只读集合只是一个带有包装器的集合，包装器可以防止对集合的修改。因此，如果对基础集合进行了更改，只读集合将反映这些更改。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . ordereddictionary . is readonly？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.ordereddictionary.isreadonly?view=netframework-4.7.2)