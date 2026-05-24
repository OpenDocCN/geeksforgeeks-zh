# C# |获取遍历 SortedSet 的枚举器

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-a-enumerator-迭代通过-sortedset/](https://www.geeksforgeeks.org/c-sharp-get-an-enumerator-that-iterates-through-the-sortedset/)

**排序集合< T >。GetEnumerator 方法**用于返回遍历 SortedSet < T >的枚举数。

**语法:**

```cs
public System.Collections.Generic.SortedSet<T>.Enumerator GetEnumerator ();
```

**返回值:**该方法返回一个枚举器，该枚举器按照排序顺序遍历排序集合< T >。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to get an IDictionaryEnumerator
// that iterates through the SortedSet
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedSet of integers
        SortedSet<int> mySortedSet = new SortedSet<int>();

        // adding elements in mySortedSet
        mySortedSet.Add(2);
        mySortedSet.Add(4);
        mySortedSet.Add(6);
        mySortedSet.Add(8);
        mySortedSet.Add(10);

        // To get an Enumerator
        // for the SortedSet
        SortedSet<int>.Enumerator em = mySortedSet.GetEnumerator();
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
2
4
6
8
10

```

**例 2:**

```cs
// C# code to get an IDictionaryEnumerator
// that iterates through the SortedSet
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedSet of integers
        SortedSet<string> mySortedSet = new SortedSet<string>();

        // adding elements in mySortedSet
        mySortedSet.Add("C#");
        mySortedSet.Add("PHP");
        mySortedSet.Add("HTML");
        mySortedSet.Add("Java");
        mySortedSet.Add("C++");

        // To get an Enumerator
        // for the SortedSet
        SortedSet<string>.Enumerator em = mySortedSet.GetEnumerator();
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
C++
HTML
Java
PHP

```

**注:**

*   C# 语言的 *foreach* 语句隐藏了枚举器的复杂性。因此，建议使用 foreach，而不是直接操作枚举器。
*   枚举数可用于读取集合中的数据，但不能用于修改基础集合。
*   *当前*返回同一对象，直到调用*移动下一个*或*重置*为止。*移动下一个*将当前设置为下一个元素。
*   只要集合保持不变，枚举数就保持有效。如果对集合进行了更改，例如添加、修改或删除元素，枚举数将无法恢复地失效，并且其行为未定义。
*   这个方法是一个 O(log n)操作。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . sorted set-1 . getenumerator？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedset-1.getenumerator?view=netframework-4.7.2)