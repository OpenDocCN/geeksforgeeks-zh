# 如何在 C# 中创建 StringDictionary

> 原文:[https://www . geeksforgeeks . org/如何创建-a-stringdictionary-in-c-sharp/](https://www.geeksforgeeks.org/how-to-create-a-stringdictionary-in-c-sharp/)

**StringDictionary()构造函数**用于初始化 StringDictionary 类的新实例，该实例将为空，并将具有默认的初始容量。 [StringDictionary](https://www.geeksforgeeks.org/c-sharp-stringdictionary-class/) 是一个专门的收藏。这个类属于`System.Collections.Specialized`命名空间。它只允许字符串键和字符串值。它存在性能问题。它实现了一个哈希表，其中键和值被强类型化为字符串而不是对象。

**语法:**

```cs
public StringDictionary ();
```

**例 1:**

```cs
// C# Program to illustrate how
// to create a StringDictionary
using System;
using System.Collections;
using System.Collections.Specialized;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // sd is the StringDictionary object
        // StringDictionary() is the constructor
        // used to initializes a new
        // instance of the StringDictionary class
        StringDictionary sd = new StringDictionary();

        // Count property is used to get the
        // number of elements in StringDictionary
        // It will give 0 as no elements
        // are present currently
        Console.WriteLine(sd.Count);
    }
}
```

**Output:**

```cs
0

```

**例 2:**

```cs
// C# Program to illustrate how
// to create a StringDictionary
using System;
using System.Collections;
using System.Collections.Specialized;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // sd is the StringDictionary object
        // StringDictionary() is the constructor
        // used to initializes a new
        // instance of the StringDictionary class
        StringDictionary sd = new StringDictionary();

        Console.Write("Before Add Method: ");

        // Count property is used to get the
        // number of elements in StringDictionary
        // It will give 0 as no elements
        // are present currently
        Console.WriteLine(sd.Count);

        // Adding key/value pairs in sd
        sd.Add("1", "C");
        sd.Add("2", "C++");
        sd.Add("3", "Java");
        sd.Add("4", "Python");
        sd.Add("5", "C#");
        sd.Add("6", "HTML");

        Console.Write("After Add Method: ");

        // Count property is used to get the
        // number of elements in sd
        Console.WriteLine(sd.Count);
    }
}
```

**Output:**

```cs
Before Add Method: 0
After Add Method: 6

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . string dictionary-ctor？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringdictionary.-ctor?view=netframework-4.7.2)