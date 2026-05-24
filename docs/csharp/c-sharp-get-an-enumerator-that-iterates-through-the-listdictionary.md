# C# |获取遍历列表字典的枚举器

> 原文:[https://www . geesforgeks . org/c-sharp-get-a-enumerator-in-iterating-through-list dictionary/](https://www.geeksforgeeks.org/c-sharp-get-an-enumerator-that-iterates-through-the-listdictionary/)

**列表词典。GetEnumerator 方法**用于返回一个 IDictionaryEnumerator，迭代遍历 ListDictionary。

**语法:**

```cs
public System.Collections.IDictionaryEnumerator GetEnumerator ();
```

**返回值:**这个方法为列表字典返回一个 [IDictionaryEnumerator](https://docs.microsoft.com/en-us/dotnet/api/system.collections.idictionaryenumerator?view=netframework-4.7.2) 。

以下程序说明了**列表词典的使用。GetEnumerator 方法**:

**例 1:**

```cs
// C# code to get an IDictionaryEnumerator
// that iterates through the ListDictionary
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a ListDictionary named myDict
        ListDictionary myDict = new ListDictionary();

        myDict.Add("Australia", "Canberra");
        myDict.Add("Belgium", "Brussels");
        myDict.Add("Netherlands", "Amsterdam");
        myDict.Add("China", "Beijing");
        myDict.Add("Russia", "Moscow");
        myDict.Add("India", "New Delhi");

        // To get an IDictionaryEnumerator
        // for the ListDictionary
        IDictionaryEnumerator myEnumerator = myDict.GetEnumerator();

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
Netherlands --> Amsterdam
China --> Beijing
Russia --> Moscow
India --> New Delhi

```

**例 2:**

```cs
// C# code to get an IDictionaryEnumerator
// that iterates through the ListDictionary
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a ListDictionary named myDict
        ListDictionary myDict = new ListDictionary();

        // Adding key/value pairs in myDict
        myDict.Add("I", "C");
        myDict.Add("II", "C++");
        myDict.Add("III", "Java");
        myDict.Add("IV", "Python");
        myDict.Add("V", "C#");

        // To get an IDictionaryEnumerator
        // for the ListDictionary
        IDictionaryEnumerator myEnumerator = myDict.GetEnumerator();

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
I --> C
II --> C++
III --> Java
IV --> Python
V --> C#

```

**注:**

*   C# 语言的 foreach 语句隐藏了枚举器的复杂性。因此，建议使用 foreach，而不是直接操作枚举器。
*   枚举数可用于读取集合中的数据，但不能用于修改基础集合。
*   *当前*返回同一对象，直到调用*移动下一个*或*重置*为止。*移动下一个*将当前设置为下一个元素。
*   只要集合保持不变，枚举数就保持有效。如果对集合进行了更改，例如添加、修改或删除元素，枚举数将无法恢复地失效，并且其行为未定义。
*   这个方法是一个 O(1)运算。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . list dictionary . getenumerator？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.listdictionary.getenumerator?view=netframework-4.7.2)