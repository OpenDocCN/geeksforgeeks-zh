# C# |获取遍历集合

的枚举器

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-a-enumerator-iterated-through-collection/](https://www.geeksforgeeks.org/c-sharp-get-an-enumerator-that-iterates-through-collectiont/)

***集合< T >。GetEnumerator 方法*** 用于获取遍历 **[集合< T >](https://www.geeksforgeeks.org/c-collection-class/)** 的枚举器。

**语法:**

```cs
public System.Collections.Generic.IEnumerator<T> GetEnumerator ();
```

**返回值:**该方法为集合< T >返回一个 IEnumerator < T >。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to get an Enumerator that
// iterates through the Collection<T>
using System;
using System.Collections.ObjectModel;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a collection of strings
        Collection<string> myColl = new Collection<string>();

        myColl.Add("A");
        myColl.Add("B");
        myColl.Add("C");
        myColl.Add("D");
        myColl.Add("E");

        // Displaying the number of elements in Collection
        Console.WriteLine("The number of elements in myColl are: "
                                                  + myColl.Count);

        // To get an Enumerator
        // for the Collection
        var enumerator = myColl.GetEnumerator();

        // If MoveNext passes the end of the
        // collection, the enumerator is positioned
        // after the last element in the collection
        // and MoveNext returns false.
        while (enumerator.MoveNext()) {

            Console.WriteLine(enumerator.Current);
        }
    }
}
```

**Output:**

```cs
The number of elements in myColl are: 5
A
B
C
D
E

```

**例 2:**

```cs
// C# code to get an Enumerator that
// iterates through the Collection<T>
using System;
using System.Collections.ObjectModel;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a collection of integers
        Collection<int> myColl = new Collection<int>();

        myColl.Add(45);
        myColl.Add(56);
        myColl.Add(78);
        myColl.Add(75);

        // Displaying the number of elements in Collection
        Console.WriteLine("The number of elements in myColl are: "
                                                  + myColl.Count);

        // To get an Enumerator
        // for the Collection
        var enumerator = myColl.GetEnumerator();

        // If MoveNext passes the end of the
        // collection, the enumerator is positioned
        // after the last element in the collection
        // and MoveNext returns false.
        while (enumerator.MoveNext()) {

            Console.WriteLine(enumerator.Current);
        }
    }
}
```

**Output:**

```cs
The number of elements in myColl are: 4
45
56
78
75

```

**注:**

*   C# 语言的 *foreach* 语句隐藏了枚举器的复杂性。因此，建议使用 *foreach* ，而不是直接操作枚举器。
*   枚举数可用于读取集合中的数据，但不能用于修改基础集合。
*   *当前*返回同一对象，直到调用*移动下一个*或*重置*为止。*移动下一个*将当前设置为下一个元素。
*   只要集合保持不变，枚举数就保持有效。如果对集合进行了更改，例如添加、修改或删除元素，枚举数将无法恢复地失效，并且其行为未定义。
*   这个方法是一个 O(1)运算。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . object model . collection-1 . getenumerator？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.objectmodel.collection-1.getenumerator?view=netframework-4.7.2)