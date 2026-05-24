# C# |获取 StringDictionary 中的键集合

> 原文:[https://www . geesforgeks . org/c-sharp-get-a-collection-in-stringdictionary/](https://www.geeksforgeeks.org/c-sharp-get-a-collection-of-keys-in-the-stringdictionary/)

**StringDictionary。Keys** 属性用于获取 StringDictionary 中的一组键。

**语法:**

```cs
public virtual System.Collections.ICollection Keys { get; }

```

**返回值:**一个[集合](https://docs.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=netframework-4.7.2)，提供字符串中的键。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to get a collection
// of keys in the StringDictionary
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
        myDict.Add("A", "Apple");
        myDict.Add("B", "Banana");
        myDict.Add("C", "Cat");
        myDict.Add("D", "Dog");

        // To copy the StringDictionary values to
        // a one-dimensional Array instance at
        // the specified index.
        String[] myKeys = new String[myDict.Count];
        myDict.Keys.CopyTo(myKeys, 0);

        // Getting a collection of keys
        // in the StringDictionary
        for (int i = 0; i < myDict.Count; i++) {
            Console.WriteLine(myKeys[i] + " " + myDict[myKeys[i]]);
        }
    }
}
```

**输出:**

```cs
d Dog
b Banana
c Cat
a Apple

```

**例 2:**

```cs
// C# code to get a collection
// of keys in the StringDictionary
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
        myDict.Add("3", "prime & odd");
        myDict.Add("2", "prime & even");
        myDict.Add("4", "non-prime & even");
        myDict.Add("9", "non-prime & odd");

        // To copy the StringDictionary values to
        // a one-dimensional Array instance at
        // the specified index.
        String[] myKeys = new String[myDict.Count];
        myDict.Keys.CopyTo(myKeys, 0);

        // Getting a collection of keys
        // in the StringDictionary
        for (int i = 0; i < myDict.Count; i++) {
            Console.WriteLine(myKeys[i] + " " + myDict[myKeys[i]]);
        }
    }
}
```

**输出:**

```cs
2 prime & even
3 prime & odd
9 non-prime & odd
4 non-prime & even

```

**注:**

*   icocollection 中键的顺序未指定，但它与 **Values** 方法返回的 icocollection 中关联值的顺序相同。
*   返回的 ICollection 不是静态副本。相反，ICollection 引用了原始 StringDictionary 中的键。因此，对 StringDictionary 的更改继续反映在 ICollection 中。
*   检索该属性的值是一个 O(1)操作。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . string dictionary . keys？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringdictionary.keys?view=netframework-4.7.2)