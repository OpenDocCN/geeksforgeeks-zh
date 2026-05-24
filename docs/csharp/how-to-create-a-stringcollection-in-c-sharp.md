# 如何在 C# 中创建字符串集合

> 原文:[https://www . geesforgeks . org/how-create-a-string collection-in-c-sharp/](https://www.geeksforgeeks.org/how-to-create-a-stringcollection-in-c-sharp/)

**StringCollection()构造函数**用于初始化 StringCollection 类的新实例。 [StringCollection 类](https://www.geeksforgeeks.org/c-sharp-stringcollection-class/)是*的新增成员。NET* 表示字符串集合的框架类库。在*系统中定义了 StringCollection 类。集合。专用*命名空间。

**语法:**

```cs
public StringCollection ();
```

**例 1:**

```cs
// C# Program to illustrate how
// to create a StringCollection
using System;
using System.Collections;
using System.Collections.Specialized;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // sc is the StringCollection object
        // StringCollection() is the constructor
        // used to initializes a new
        // instance of the StringCollection class
        StringCollection sc = new StringCollection();

        // Count property is used to get the
        // number of elements in StringCollection
        // It will give 0 as no elements
        // are present currently
        Console.WriteLine("Number of elements: "+
                                      sc.Count);
    }
}
```

**Output:**

```cs
Number of elements: 0

```

**例 2:**

```cs
// C# Program to illustrate how
// to create a StringCollection
using System;
using System.Collections;
using System.Collections.Specialized;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // sc is the StringCollection object
        // StringCollection() is the constructor
        // used to initializes a new
        // instance of the StringCollection class
        StringCollection sc = new StringCollection();

        Console.Write("Before Add Method: ");

        // Count property is used to get the
        // number of elements in StringCollection
        // It will give 0 as no elements
        // are present currently
        Console.WriteLine(sc.Count);

        Console.Write("After Add Method: ");

        // Adding elements in StringCollection
        sc.Add("A");
        sc.Add("B");
        sc.Add("C");
        sc.Add("D");
        sc.Add("E");

        // Count property is used to get the
        // number of elements in ld
        Console.WriteLine(sc.Count);
    }
}
```

**Output:**

```cs
Before Add Method: 0
After Add Method: 5

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . string collection-ctor？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringcollection.-ctor?view=netframework-4.7.2)