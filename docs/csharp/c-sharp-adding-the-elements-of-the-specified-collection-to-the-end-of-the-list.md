# C# |将指定集合的元素添加到列表的末尾

> 原文:[https://www . geeksforgeeks . org/c-sharp-将指定集合的元素添加到列表末尾/](https://www.geeksforgeeks.org/c-sharp-adding-the-elements-of-the-specified-collection-to-the-end-of-the-list/)

**列表< T >。AddRange(IEnumerable < T >)方法**用于将指定集合的元素添加到列表< T >的末尾。

**列表属性:**

*   它不同于数组。列表可以动态调整大小，但数组不能。
*   列表类可以接受 null 作为引用类型的有效值，并且它还允许重复的元素。
*   如果 **[计数](https://www.geeksforgeeks.org/c-get-the-number-of-elements-actually-contained-in-the-arraylist/)** 等于 **[容量，](https://www.geeksforgeeks.org/c-capacity-of-a-list/)** 则列表的容量通过重新分配内部数组自动增加。在添加新元素之前，现有元素将被复制到新数组中。

**语法:**

```cs
public void AddRange (System.Collections.Generic.IEnumerable<T> collection);

```

**参数:**

> **集合:**是指定的集合，其元素将被添加到列表< T >的末尾。

**异常:**如果集合为空，这个方法会给出 *ArgumentNullException* 。

**注意:**集合本身不能为空，但是如果类型 T 是引用类型，它可以包含为空的元素。集合中元素的顺序始终保留在列表<中。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to illustrate the
// List.AddRange Method
using System;
using System.Collections.Generic;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a List of Strings
        List<String> firstlist = new List<String>();

        // adding elements in firstlist
        firstlist.Add("Geeks");
        firstlist.Add("GFG");
        firstlist.Add("C#");
        firstlist.Add("Tutorials");

        Console.WriteLine("Before AddRange Method");
        Console.WriteLine();

        // displaying the item of List
        foreach(String str in firstlist)
        {
            Console.WriteLine(str);
        }

        Console.WriteLine("\nAfter AddRange Method\n");

        // Here we are using AddRange method
        // Which adds the elements of firstlist
        // Collection in firstlist again i.e.
        // we have copied the whole firstlist
        // in it
        firstlist.AddRange(firstlist);

        // displaying the item of List
        foreach(String str in firstlist)
        {
            Console.WriteLine(str);
        }
    }
}
```

**输出:**

```cs
Before AddRange Method

Geeks
GFG
C#
Tutorials

After AddRange Method

Geeks
GFG
C#
Tutorials
Geeks
GFG
C#
Tutorials

```

**例 2:**

```cs
// C# program to illustrate the
// List.AddRange Method
using System;
using System.Collections.Generic;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a List of Strings
        List<String> firstlist = new List<String>();

        // adding elements in firstlist
        firstlist.Add("Geeks");
        firstlist.Add("GFG");
        firstlist.Add("C#");
        firstlist.Add("Tutorials");

        Console.WriteLine("Before AddRange Method");
        Console.WriteLine();

        // displaying the item of List
        foreach(String str in firstlist)
        {
            Console.WriteLine(str);
        }

        Console.WriteLine("\nAfter AddRange Method\n");

        // taking array of String
        string[] str_add = { "Collections",
                             "Generic",
                             "List" };

        // here we are adding the elements
        // of the str_add to the end of
        // the List<T>.
        firstlist.AddRange(str_add);

        // displaying the item of List
        foreach(String str in firstlist)
        {
            Console.WriteLine(str);
        }
    }
}
```

**输出:**

```cs
Before AddRange Method

Geeks
GFG
C#
Tutorials

After AddRange Method

Geeks
GFG
C#
Tutorials
Collections
Generic
List

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . list-1 . add range？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.addrange?view=netframework-4.7.2)