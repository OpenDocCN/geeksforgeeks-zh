# C# |如何获取列表中最后一个符合指定条件的元素

> 原文:[https://www . geesforgeks . org/c-sharp-如何获得符合指定条件的列表中最后出现的元素/](https://www.geeksforgeeks.org/c-sharp-how-to-get-the-last-occurrence-of-the-element-in-the-list-that-match-the-specified-conditions/)

**列表< T >。FindLast(谓词< T >)方法**用于搜索与指定谓词定义的条件相匹配的元素，并返回该元素在整个列表< T >中的最后一次出现。

**列表属性:**

*   它不同于数组。列表可以动态调整大小，但数组不能。
*   列表类可以接受 null 作为引用类型的有效值，并且它还允许重复的元素。
*   如果计数等于容量，则列表的容量会通过重新分配内部数组而自动增加。在添加新元素之前，现有元素将被复制到新数组中。

**语法:**

```cs
public T FindLast (Predicate<T> match);

```

**参数:**

> **匹配:**是谓词< T >委托定义了要搜索的元素的条件。

**返回值:**如果找到元素，那么这个方法将返回最后一个与指定谓词定义的条件相匹配的元素，否则它将返回类型 T 的默认值

**异常:**如果匹配为空，该方法将给出 *ArgumentNullException* 。

以下程序说明了**列表< T >的使用。FindLast(谓词< T >)方法:**

**例 1:**

```cs
// C# Program to get the last occurrence
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
    firstlist.Add(4);
    firstlist.Add(2);
    firstlist.Add(7);
    firstlist.Add(2);
    firstlist.Add(6);
    firstlist.Add(4);
    firstlist.Add(3);

    Console.WriteLine("Elements Present in List:\n");

    int p = 0;

    // Displaying the elements of List
    foreach(int k in firstlist)
    {
        Console.Write("At Position {0}: ", p);
        Console.WriteLine(k);
        p++;
    }

    Console.WriteLine(" ");

    // Will give the last occurrence of the
    // element of firstlist that match the
    // conditions defined by predicate
    Console.Write("Index of Last element that fullfill the conditions: ");
    Console.WriteLine(firstlist.LastIndexOf(firstlist.FindLast(isEven)));
    Console.Write("Element is: ");
    Console.Write((firstlist.FindLast(isEven)));
}
}
```

**Output:**

```cs
Elements Present in List:

At Position 0: 4
At Position 1: 2
At Position 2: 7
At Position 3: 2
At Position 4: 6
At Position 5: 4
At Position 6: 3

Index of Last element that fullfill the conditions: 5
Element is: 4

```

**例 2:**

```cs
// C# Program to get the last occurrence
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
    firstlist.Add(17);
    firstlist.Add(19);
    firstlist.Add(21);
    firstlist.Add(9);
    firstlist.Add(75);
    firstlist.Add(19);
    firstlist.Add(73);

    Console.WriteLine("Elements Present in List:\n");

    int p = 0;

    // Displaying the elements of List
    foreach(int k in firstlist)
    {
        Console.Write("At Position {0}: ", p);
        Console.WriteLine(k);
        p++;
    }

    Console.WriteLine(" ");

    // it will return index -1 as no element
    // found in the list which specified
    // the conditions and so element value
    // will be 0 as the list contains Integers
    Console.Write("Index of Last element that fullfill the conditions: ");
    Console.WriteLine(firstlist.LastIndexOf(firstlist.FindLast(isEven)));
    Console.Write("Element is: ");
    Console.Write((firstlist.FindLast(isEven)));
}
}
```

**Output:**

```cs
Elements Present in List:

At Position 0: 17
At Position 1: 19
At Position 2: 21
At Position 3: 9
At Position 4: 75
At Position 5: 19
At Position 6: 73

Index of Last element that fullfill the conditions: -1
Element is: 0

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . list-1 . find last？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.findlast?view=netframework-4.7.2)