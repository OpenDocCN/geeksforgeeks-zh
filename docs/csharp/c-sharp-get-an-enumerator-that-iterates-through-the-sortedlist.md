# C# |获取遍历 SortedList 的枚举器

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-a-enumerator-迭代通过-sortedlist/](https://www.geeksforgeeks.org/c-sharp-get-an-enumerator-that-iterates-through-the-sortedlist/)

**排序列表。GetEnumerator 方法**用于一个 [IDictionaryEnumerator](https://docs.microsoft.com/en-us/dotnet/api/system.collections.idictionaryenumerator?view=netframework-4.7.2) 对象，该对象迭代一个 SortedList 对象。

**语法:**

```cs
public virtual System.Collections.IDictionaryEnumerator GetEnumerator ();
```

**返回值:**这个方法为 SortedList 对象返回一个 IDictionaryEnumerator 对象。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to get IDictionaryEnumerator object
// that iterates through a SortedList object
using System;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a SortedList of integers
        SortedList mylist = new SortedList();

        // Adding elements to SortedList
        mylist.Add("1", "C++");
        mylist.Add("2", "Java");
        mylist.Add("3", "DSA");
        mylist.Add("4", "Python");
        mylist.Add("5", "C#");

        // To get an IDictionaryEnumerator
        // for the SortedList
        IDictionaryEnumerator myEnumerator = 
                             mylist.GetEnumerator();

        // If MoveNext passes the end of the
        // collection, the enumerator is positioned
        // after the last element in the collection
        // and MoveNext returns false.
        while (myEnumerator.MoveNext())
            Console.WriteLine(myEnumerator.Key + " --> "
                              + myEnumerator.Value);
    }
}
```

**Output:**

```cs
1 --> C++
2 --> Java
3 --> DSA
4 --> Python
5 --> C#

```

**例 2:**

```cs
// C# code to get IDictionaryEnumerator object
// that iterates through a SortedList object
using System;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a SortedList of integers
        SortedList mylist = new SortedList();

        // Adding elements to SortedList
        mylist.Add("Australia", "Canberra");
        mylist.Add("Belgium", "Brussels");
        mylist.Add("Netherlands", "Amsterdam");
        mylist.Add("China", "Beijing");
        mylist.Add("Russia", "Moscow");
        mylist.Add("India", "New Delhi");

        // To get an IDictionaryEnumerator
        // for the SortedList
        IDictionaryEnumerator myEnumerator = 
                             mylist.GetEnumerator();

        // If MoveNext passes the end of the
        // collection, the enumerator is positioned
        // after the last element in the collection
        // and MoveNext returns false.
        while (myEnumerator.MoveNext())
            Console.WriteLine(myEnumerator.Key + " --> "
                              + myEnumerator.Value);
    }
}
```

**Output:**

```cs
Australia --> Canberra
Belgium --> Brussels
China --> Beijing
India --> New Delhi
Netherlands --> Amsterdam
Russia --> Moscow

```

**注:**

*   C# 语言的 *foreach* 语句隐藏了枚举器的复杂性。因此，建议使用 foreach，而不是直接操作枚举器。
*   枚举数可用于读取集合中的数据，但不能用于修改基础集合。
*   *当前*返回同一对象，直到调用*移动下一个*或*重置*为止。*移动下一个*将当前设置为下一个元素。
*   只要集合保持不变，枚举数就保持有效。如果对集合进行了更改，例如添加、修改或删除元素，枚举数将无法恢复地失效，并且其行为未定义。
*   这个方法是一个 O(1)运算。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . sorted list . getenumerator？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.sortedlist.getenumerator?view=netframework-4.7.2)