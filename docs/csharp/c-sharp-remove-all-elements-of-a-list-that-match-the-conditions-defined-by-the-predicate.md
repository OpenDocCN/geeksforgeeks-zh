# C# |移除列表中所有与谓词

定义的条件相匹配的元素

> 原文:[https://www . geeksforgeeks . org/c-sharp-移除符合谓词定义的条件的列表中的所有元素/](https://www.geeksforgeeks.org/c-sharp-remove-all-elements-of-a-list-that-match-the-conditions-defined-by-the-predicate/)

**列表< T >。RemoveAll(谓词< T >)方法**用于移除所有与指定谓词定义的条件相匹配的元素。

**列表属性:**

*   它不同于数组。列表可以动态调整大小，但数组不能。
*   列表类可以接受 null 作为引用类型的有效值，并且它还允许重复的元素。
*   如果计数等于容量，则通过重新分配内部阵列，列表的容量会自动增加。在添加新元素之前，现有元素将被复制到新数组中。

**语法:**

```cs
public int RemoveAll (Predicate<T> match);
```

**参数:**

> **匹配:**是谓词< T >委托定义了要移除的元素的条件。

**返回值:**该方法返回要从列表<中删除的元素数量>。

**异常:**如果*匹配*为空，此方法将给出 *ArgumentNullException* 。

以下程序说明了**列表< T >的使用。移除所有(谓词< T >)方法:**

**例 1:**

```cs
// C# Program to remove all elements of
// a List that match the conditions
// defined by the predicate
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
        for (int i = 1; i <= 10; i++) {
            firstlist.Add(i);
        }

        Console.WriteLine("Elements Present in List:\n");

        // Displaying the elements of List
        foreach (int k in firstlist)
        {
            Console.WriteLine(k);
        }

        Console.WriteLine(" ");

        Console.Write("Number of Elements Removed: ");

        // Removing the elements which is even
        // This will return 5 as it removed 5
        // even elements from the list
        Console.WriteLine(firstlist.RemoveAll(isEven));

        Console.WriteLine(" ");

        Console.WriteLine("Remaining Elements in List:");

        // Displaying the elements of List
        foreach (int k in firstlist)
        {
            Console.WriteLine(k);
        }
    }
}
```

**输出:**

```cs
Elements Present in List:

1
2
3
4
5
6
7
8
9
10

Number of Elements Removed: 5

Remaining Elements in List:
1
3
5
7
9

```

**例 2:**

```cs
// C# Program to remove all elements of
// a List that match the conditions
// defined by the predicate
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

        // Adding items to List
        firstlist.Add(13);
        firstlist.Add(17);
        firstlist.Add(19);
        firstlist.Add(11);

        Console.WriteLine("Elements Present in List:\n");

        // Displaying the elements of List
        foreach(int k in firstlist)
        {
            Console.WriteLine(k);
        }

        Console.WriteLine(" ");

        Console.Write("Number of Elements Removed: ");

        // Removing the elements which is even
        // This will return 0 as it no elements
        // are even in List
        Console.WriteLine(firstlist.RemoveAll(isEven));

        Console.WriteLine(" ");

        Console.WriteLine("Remaining Elements in List:");

        // Displaying the elements of List
        foreach (int k in firstlist)
        {
            Console.WriteLine(k);
        }
    }
}
```

**输出:**

```cs
Elements Present in List:

13
17
19
11

Number of Elements Removed: 0

Remaining Elements in List:
13
17
19
11

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . list-1 . removeall？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.removeall?view=netframework-4.7.2)