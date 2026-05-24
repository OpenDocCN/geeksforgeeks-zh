# C# |从 OrderedDictionary 中删除所有元素

> 原文:[https://www . geeksforgeeks . org/c-sharp-remove-all-elements-from-ordered dictionary/](https://www.geeksforgeeks.org/c-sharp-remove-all-elements-from-ordereddictionary/)

**OrderedDictionary。Clear** 方法用于从 OrderedDictionary 集合中移除所有元素。

**语法:**

```cs
public void Clear ();

```

**异常:**如果 OrderedDictionary 集合是只读的，那么它将抛出***NotSupportedException***。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to remove all elements
// from OrderedDictionary
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
        Console.WriteLine("Number of elements are : " + myDict.Count);

        // Displaying the elements in myDict
        foreach(DictionaryEntry de in myDict)
            Console.WriteLine(de.Key + " -- " + de.Value);

        // Removing all elements from OrderedDictionary
        myDict.Clear();

        // Displaying the number of element initially
        Console.WriteLine("Number of elements are : " + myDict.Count);

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
Number of elements are : 0

```

**例 2:**

```cs
// C# code to remove all elements
// from OrderedDictionary
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
        Console.WriteLine("Number of elements are : " + myDict.Count);

        // Displaying the elements in myDict
        foreach(DictionaryEntry de in myDict)
            Console.WriteLine(de.Key + " -- " + de.Value);

        // Removing all elements from OrderedDictionary
        myDict.Clear();

        // Displaying the number of element initially
        Console.WriteLine("Number of elements are : " + myDict.Count);

        // Displaying the elements in myDict
        foreach(DictionaryEntry de in myDict)
            Console.WriteLine(de.Key + " -- " + de.Value);
    }
}
```

**输出:**

```cs
Number of elements are : 4
A -- Apple
B -- Banana
C -- Cat
D -- Dog
Number of elements are : 0

```

**注:**

*   调用**清除**方法后，**计数**属性设置为零。
*   还会释放对集合元素中其他对象的引用。
*   调用此方法不会改变字典的容量。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . ordered dictionary . clear？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.ordereddictionary.clear?view=netframework-4.7.2)