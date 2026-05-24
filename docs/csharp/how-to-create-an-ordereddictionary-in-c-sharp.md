# 如何在 C# 中创建有序字典

> 原文:[https://www . geeksforgeeks . org/how-to-create-ordered dictionary-in-c-sharp/](https://www.geeksforgeeks.org/how-to-create-an-ordereddictionary-in-c-sharp/)

**OrderedDictionary()构造函数**用于初始化 OrderedDictionary 类的新实例，该实例将为空，并将具有默认的初始容量。[orderedddictionary 类](https://www.geeksforgeeks.org/c-sharp-ordereddictionary-class/)表示可由键或索引访问的键/值对的集合。它存在于`System.Collections.Specialized`命名空间中。

**语法:**

```cs
public OrderedDictionary();
```

**例 1:**

```cs
// C# Program to illustrate how
// to create a OrderedDictionary
using System;
using System.Collections;
using System.Collections.Specialized;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // od is the OrderedDictionary object
        // OrderedDictionary() is the constructor
        // used to initializes a new
        // instance of the OrderedDictionary class
        OrderedDictionary od = new OrderedDictionary();

        // Count property is used to get the
        // number of elements in OrderedDictionary
        // It will give 0 as no elements
        // are present currently
        Console.WriteLine("The number of elements: "
                                           +od.Count);
    }
}
```

**Output:**

```cs
The number of elements: 0

```

**例 2:**

```cs
// C# Program to illustrate how
// to create a OrderedDictionary
using System;
using System.Collections;
using System.Collections.Specialized;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // od is the OrderedDictionary object
        // OrderedDictionary() is the constructor
        // used to initializes a new
        // instance of the OrderedDictionary class
        OrderedDictionary od = new OrderedDictionary();

        Console.Write("Before Add Method: ");

        // Count property is used to get the
        // number of elements in OrderedDictionary
        // It will give 0 as no elements
        // are present currently
        Console.WriteLine(od.Count);

        // Adding key/value pairs in od
        od.Add("1", "C");
        od.Add("2", "C++");
        od.Add("3", "Java");
        od.Add("4", "C#");

        Console.Write("After Add Method: ");

        // Count property is used to get the
        // number of elements in ld
        Console.WriteLine(od.Count);
    }
}
```

**Output:**

```cs
Before Add Method: 0
After Add Method: 4

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . orderedddictionary-ctor？view = net framework-4 . 7 . 2 # System _ Collections _ Specialized _ OrderedDictionary _ ctor](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.ordereddictionary.-ctor?view=netframework-4.7.2# System_Collections_Specialized_OrderedDictionary__ctor)