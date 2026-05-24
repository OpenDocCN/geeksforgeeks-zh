# C# |列表中符合指定条件的第一个匹配项

> 原文:[https://www . geesforgeks . org/c-sharp-符合指定条件的列表中第一次出现/](https://www.geeksforgeeks.org/c-sharp-first-occurrence-in-the-list-that-matches-the-specified-conditions/)

**列表< T >。Find(谓词< T >)方法**用于搜索与指定谓词定义的条件相匹配的元素，并返回该元素在整个列表< T >中的第一次出现。

**列表属性:**

*   它不同于数组。列表可以动态调整大小，但数组不能。
*   列表类可以接受 null 作为引用类型的有效值，并且它还允许重复的元素。
*   如果 **[计数](https://www.geeksforgeeks.org/c-count-the-total-number-of-elements-in-the-list/)** 变为等于 **[容量](https://www.geeksforgeeks.org/c-capacity-of-a-list/)** ，则列表的容量通过重新分配内部数组而自动增加。在添加新元素之前，现有元素将被复制到新数组中。

**语法:**

```cs
public T Find (Predicate<T> match);

```

**参数:**

> **匹配:**是谓词委托定义了要搜索的元素的条件。

**返回值:**如果找到元素，那么这个方法将返回第一个与指定谓词定义的条件相匹配的元素，否则它将返回类型 T 的默认值

**异常:**如果匹配为空，该方法将给出 *ArgumentNullException* 。

以下程序说明了**列表< T >的使用。查找(谓词< T >)方法:**

**例 1:**

```cs
// C# Program to get the first occurrence
// of the element that match the specified
// conditions defined by the predicate
using System;
using System.Collections;
using System.Collections.Generic;

class Geeks {

    // function which checks whether an
    // element is even or not. Or you can
    // say it is the specified condition
    private static bool isEven(int i)
    {
        return ((i % 2) == 0);
    }

    // Main Method
    public static void Main(String[] args)
    {

        // Creating an List<T> of Integers
        List<int> firstlist = new List<int>();

        // Adding elements to List
        firstlist.Add(2);
        firstlist.Add(4);
        firstlist.Add(7);
        firstlist.Add(2);
        firstlist.Add(6);
        firstlist.Add(2);
        firstlist.Add(2);

        Console.WriteLine("Elements Present in List:\n");

        // Displaying the elements of List
        foreach(int k in firstlist)
        {
            Console.WriteLine(k);
        }

        Console.WriteLine(" ");

        Console.Write("Result: ");

        // Will give the first occurrence of the
        // element of firstlist that match the
        // conditions defined by predicate
        Console.WriteLine(firstlist.Find(isEven));
    }
}
```

**输出:**

```cs
Elements Present in List:

2
4
7
2
6
2
2

Result: 2

```

**例 2:**

```cs
// C# Program to get the first occurrence
// of the element that match the specified
// conditions defined by the predicate
using System;
using System.Collections;
using System.Collections.Generic;

class Geeks {

    // function which checks whether an
    // element is even or not. Or you can
    // say it is the specified condition
    private static bool isEven(int i)
    {
        return ((i % 2) == 0);
    }

    // Main Method
    public static void Main(String[] args)
    {

        // Creating an List<T> of Integers
        List<int> firstlist = new List<int>();

        // Adding elements to List
        firstlist.Add(5);
        firstlist.Add(7);
        firstlist.Add(9);
        firstlist.Add(11);
        firstlist.Add(3);
        firstlist.Add(17);
        firstlist.Add(19);

        Console.WriteLine("Elements Present in List:\n");

        // Displaying the elements of List
        foreach(int k in firstlist)
        {
            Console.WriteLine(k);
        }

        Console.WriteLine(" ");

        Console.Write("Result: ");

        // Will give the first occurrence of the
        // element of firstlist that match the
        // conditions defined by predicate
        // No match found so it will return 0
        Console.WriteLine(firstlist.Find(isEven));
    }
}
```

**输出:**

```cs
Elements Present in List:

5
7
9
11
3
17
19

Result: 0

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . list-1 . find？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.find?view=netframework-4.7.2)