# C# |检查 StringDictionary 是否同步(线程安全)

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-stringdictionary-is-synchronized-thread-safe/](https://www.geeksforgeeks.org/c-sharp-check-if-stringdictionary-is-synchronized-thread-safe/)

**StringDictionary。IsSynchronized** 属性用于获取一个值，该值指示对 StringDictionary 的**访问是否同步(线程安全)**。

**语法:**

```cs
public virtual bool IsSynchronized { get; }

```

**返回值:**如果对 StringDictionary 的访问是同步的(线程安全的)，这个方法返回*真*，否则返回*假*。

**示例:**

```cs
// C# code to check if StringDictionary
// is synchronized (thread safe)
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
        myDict.Add("E", "Elephant");

        // Checking if StringDictionary
        // is synchronized (thread safe)
        Console.WriteLine(myDict.IsSynchronized);
    }
}
```

**输出:**

```cs
False

```

**注:**

*   检索该属性的值是一个 O(1)操作。
*   StringDictionary 实例未同步。派生类可以使用 [SyncRoot](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringdictionary.syncroot?view=netframework-4.7.2) 属性提供 StringDictionary 的同步版本。

**参考:**
[https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . stringdictionary . is synchronized](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringdictionary.issynchronized?view=netframework-4.7.2)