# C# |获取遍历 HashSet 的枚举器

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-enumerator-it-迭代-hashsett/](https://www.geeksforgeeks.org/c-sharp-getting-an-enumerator-that-iterates-through-hashsett/)

**HashSet < T >。GetEnumerator 方法**用于获取遍历一个 [HashSet](https://www.geeksforgeeks.org/c-sharp-hashset-class/) 对象的枚举器。

**语法:**

> 公共系统。集合.通用. HashSet <t>。枚举器 GetEnumerator()；</t>

**返回值:**为*返回`HashSet<T>.Enumerator`对象，为<返回>对象，为*返回>对象。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to get an enumerator that
// iterates through the HashSet<T>
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HashSet<T> of strings
        HashSet<string> mySet = new HashSet<string>();

        // Inserting elements in HashSet
        mySet.Add("DS");
        mySet.Add("C++");
        mySet.Add("Java");
        mySet.Add("C#");

        // To get an Enumerator
        // for the HashSet<T>.
        HashSet<string>.Enumerator em = mySet.GetEnumerator();
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

**Output:**

```cs
DS
C++
Java
C#

```

**例 2:**

```cs
// C# code to get an enumerator that
// iterates through the HashSet<T>
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HashSet of integers
        HashSet<int> mySet1 = new HashSet<int>();

        // Inserting elements in HashSet
        for (int i = 1; i <= 10; i++)
            mySet1.Add(2 * i);

        // To get an Enumerator
        // for the HashSet<T>.
        HashSet<int>.Enumerator em = mySet1.GetEnumerator();
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

**Output:**

```cs
2
4
6
8
10
12
14
16
18
20

```

**注:**

*   C# 语言的 *foreach* 语句隐藏了枚举器的复杂性。因此，建议使用 *foreach* ，而不是直接操作枚举器。
*   枚举数可用于读取集合中的数据，但不能用于修改基础集合。
*   *当前*返回同一对象，直到调用*移动下一个*或*重置*为止。*移动下一个*将*电流*设置为下一个元素。
*   只要集合保持不变，枚举数就保持有效。如果对集合进行了更改，例如添加、修改或删除元素，枚举数将无法恢复地失效，并且其行为未定义。
*   这个方法是一个 O(1)运算。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . hashset-1 . getenumerator？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.hashset-1.getenumerator?view=netframework-4.7.2)