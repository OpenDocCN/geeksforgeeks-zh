# C# |获取字符串中的值集合

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-a-collection-in-stringdictionary/](https://www.geeksforgeeks.org/c-sharp-get-a-collection-of-values-in-the-stringdictionary/)

**StringDictionary。Values** 属性用于获取 StringDictionary 中的值集合。

**语法:**

```cs
public virtual System.Collections.ICollection Values { get; }

```

**返回值:**一个[集合](https://docs.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=netframework-4.7.2)，提供字符串中的值。

**例 1:**

```cs
// C# code to get a collection
// of values in the StringDictionary
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

        // Getting a collection of values
        // in the StringDictionary
        foreach(string val in myDict.Values)
        {
            Console.WriteLine(val);
        }
    }
}
```

**输出:**

```cs
Dog
Banana
Cat
Apple

```

**例 2:**

```cs
// C# code to get a collection
// of values in the StringDictionary
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

        // Getting a collection of values
        // in the StringDictionary
        foreach(string val in myDict.Values)
        {
            Console.WriteLine(val);
        }
    }
}
```

**输出:**

```cs
prime & even
prime & odd
non-prime & odd
non-prime & even

```

**注:**

*   icocollection 中值的顺序未指定，但它与 **Keys** 方法返回的 icocollection 中关联键的顺序相同。
*   返回的 ICollection 不是静态副本。相反，ICollection 引用了原始 StringDictionary 中的值。因此，对 StringDictionary 的更改继续反映在 ICollection 中。
*   检索该属性的值是一个 O(1)操作。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . string dictionary . values？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringdictionary.values?view=netframework-4.7.2)