# C# |获取遍历列表的枚举器

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-一个遍历列表的枚举器/](https://www.geeksforgeeks.org/c-sharp-get-an-enumerator-that-iterates-through-the-list/)

**列表< T >。GetEnumerator 方法**用于返回遍历列表< T >的枚举数。

**语法:**

```cs
public System.Collections.Generic.List<T>.Enumerator GetEnumerator ();
```

**返回值:**返回一个列表< T >列表的枚举器< T >。

以下程序说明了**列表< T >的使用。GetEnumerator 方法:**

**例 1:**

```cs
// C# code to get an enumerator
// that iterates through the List<T>.
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a List of int
        List<int> mylist = new List<int>();

        // Inserting elements into List
        mylist.Add(45);
        mylist.Add(78);
        mylist.Add(32);
        mylist.Add(231);
        mylist.Add(123);
        mylist.Add(76);
        mylist.Add(726);
        mylist.Add(716);
        mylist.Add(876);

        // To get an Enumerator
        // for the List.
        List<int>.Enumerator em = mylist.GetEnumerator();
        display(em);
    }

    // display method
    static void display(IEnumerator<int> em)
    {
        while (em.MoveNext()) {
            int val = em.Current;
            Console.WriteLine(val);
        }
    }
}
```

**输出:**

```cs
45
78
32
231
123
76
726
716
876

```

**例 2:**

```cs
// C# code to get an enumerator
// that iterates through the List<T>.
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a List of string
        List<string> mylist = new List<string>();

        // Inserting elements into List
        mylist.Add("C#");
        mylist.Add("Java");
        mylist.Add("C");
        mylist.Add("C++");

        // To get an Enumerator
        // for the List.
        List<string>.Enumerator em = mylist.GetEnumerator();
        display(em);
    }

    // display method
    static void display(IEnumerator<string> em)
    {
        while (em.MoveNext()) {
            string val = em.Current;
            Console.WriteLine(val);
        }
    }
}
```

**输出:**

```cs
C#
Java
C
C++

```

**注:**

*   C# 语言的 **foreach** 语句隐藏了枚举器的复杂性。因此，建议使用 foreach，而不是直接操作枚举器。
*   枚举数可用于读取集合中的数据，但不能用于修改基础集合。
*   **当前**返回同一对象，直到调用**移动下一个**或**重置**为止。移动下一个将当前设置为下一个元素。
*   只要集合保持不变，枚举数就保持有效。如果对集合进行了更改，例如添加、修改或删除元素，枚举数将无法恢复地失效，并且其行为未定义。
*   这个方法是一个 O(1)运算。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . list-1 . getenumerator？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.getenumerator?view=netframework-4.7.2)