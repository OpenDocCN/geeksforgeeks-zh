# 如何在 C# 中创建列表字典

> 原文:[https://www . geesforgeks . org/如何创建 c-sharp 中的 list dictionary/](https://www.geeksforgeeks.org/how-to-create-a-listdictionary-in-c-sharp/)

**ListDictionary()构造函数**用于使用默认比较器初始化 ListDictionary 类的一个新的空实例。[列表词典](https://www.geeksforgeeks.org/c-sharp-listdictionary-class/)是一个专门的集合。它属于`System.Collections.Specialized`命名空间。此类型表示非泛型字典类型。它是用链表实现的。这个类是小列表的字典集合(`System.Collections.IDictionary`)的简单实现。

**语法:**

```cs
public ListDictionary ();
```

**例 1:**

```cs
// C# Program to illustrate how
// to create a ListDictionary
using System;
using System.Collections;
using System.Collections.Specialized;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // ld is the ListDictionary object
        // ListDictionary() is the constructor
        // used to initializes a new
        // instance of the ListDictionary class
        ListDictionary ld = new ListDictionary();

        // Count property is used to get the
        // number of elements in ListDictionary
        // It will give 0 as no elements
        // are present currently
        Console.WriteLine("The number of elements: "+ 
                                           ld.Count);
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
// to create a ListDictionary
using System;
using System.Collections;
using System.Collections.Specialized;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // ld is the ListDictionary object
        // ListDictionary() is the constructor
        // used to initializes a new
        // instance of the ListDictionary class
        ListDictionary ld = new ListDictionary();

        Console.Write("Before Add Method: ");

        // Count property is used to get the
        // number of elements in ListDictionary
        // It will give 0 as no elements
        // are present currently
        Console.WriteLine(ld.Count);

        // Adding key/value pairs in ld
        ld.Add("Australia", "Canberra");
        ld.Add("Belgium", "Brussels");
        ld.Add("Netherlands", "Amsterdam");
        ld.Add("China", "Beijing");
        ld.Add("Russia", "Moscow");
        ld.Add("India", "New Delhi");

        Console.Write("After Add Method: ");

        // Count property is used to get the
        // number of elements in ld
        Console.WriteLine(ld.Count);
    }
}
```

**Output:**

```cs
Before Add Method: 0
After Add Method: 6

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . list dictionary-ctor？view = net framework-4 . 7 . 2 # System _ Collections _ Specialized _ list dictionary _ ctor](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.listdictionary.-ctor?view=netframework-4.7.2# System_Collections_Specialized_ListDictionary__ctor)