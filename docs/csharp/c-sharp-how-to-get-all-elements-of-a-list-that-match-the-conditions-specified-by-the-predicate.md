# C# |如何获取列表中符合谓词

指定条件的所有元素

> 原文:[https://www . geesforgeks . org/c-sharp-如何获得符合谓词指定条件的列表中的所有元素/](https://www.geeksforgeeks.org/c-sharp-how-to-get-all-elements-of-a-list-that-match-the-conditions-specified-by-the-predicate/)

**列表< T >。FindAll(谓词< T >)方法**用于获取与指定谓词定义的条件相匹配的所有元素。

**列表属性:**

*   它不同于数组。列表可以动态调整大小，但数组不能。
*   列表类可以接受 null 作为引用类型的有效值，并且它还允许重复的元素。
*   如果 **[计数](https://www.geeksforgeeks.org/c-count-the-total-number-of-elements-in-the-list/)** 变为等于 **[容量](https://www.geeksforgeeks.org/c-capacity-of-a-list/)** ，则列表的容量通过重新分配内部数组而自动增加。在添加新元素之前，现有元素将被复制到新数组中。

**语法:**

```cs
public System.Collections.Generic.List<T> FindAll (Predicate<T> match);
```

**参数:**

> **匹配:**是谓词< T >委托定义了要搜索的元素的条件。

**返回值:**这个方法返回一个列表< T >包含所有符合指定谓词定义的条件的元素，否则返回一个空列表< T >。

**异常:**如果*匹配*为空，此方法将给出 *ArgumentNullException* 。

以下程序说明了**列表< T >的使用。FindAll(谓词< T >)方法:**

**例 1:**

```cs
// C# Program to get all the element that
// match the specified conditions defined
// by the predicate
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
        firstlist.Add(3);
        firstlist.Add(2);
        firstlist.Add(4);

        Console.WriteLine("Elements Present in List:\n");

        // Displaying the elements of List
        foreach(int k in firstlist)
        {
            Console.WriteLine(k);
        }

        Console.WriteLine(" ");

        Console.Write("Elements that Match: \n");

        // Will give the List of Elements that
        // match the conditions defined by predicate
        List<int> Result = new List<int>(firstlist.FindAll(isEven));

        foreach(int i in Result)
        {
            Console.WriteLine(i);
        }
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
3
2
4

Elements that Match: 
2
4
2
2
4

```

**例 2:**

```cs
// C# Program to get all the element that
// match the specified conditions defined
// by the predicate
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
        firstlist.Add(77);
        firstlist.Add(15);
        firstlist.Add(9);
        firstlist.Add(3);
        firstlist.Add(7);
        firstlist.Add(57);

        Console.WriteLine("Elements Present in List:\n");

        // Displaying the elements of List
        foreach(int k in firstlist)
        {
            Console.WriteLine(k);
        }

        Console.WriteLine(" ");

        Console.Write("Result is: ");

        // Will give the List of Elements that
        // match the conditions defined by predicate
        // Here no even number found in the list
        // so it wil return an empty list
        List<int> Result = new List<int>(firstlist.FindAll(isEven));

        // checking for the resultant
        // Elements in the List
        if ((Result.Count) == 0) {
            Console.WriteLine("No Match Found");
        }
    }
}
```

**输出:**

```cs
Elements Present in List:

17
77
15
9
3
7
57

Result is: No Match Found

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . list-1 . find all？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.findall?view=netframework-4.7.2)