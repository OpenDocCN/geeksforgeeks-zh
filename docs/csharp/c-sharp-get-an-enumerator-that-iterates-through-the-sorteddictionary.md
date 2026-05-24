# C# |获取遍历 SortedDictionary 的枚举器

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-a-enumerator-迭代通过-sorteddictionary/](https://www.geeksforgeeks.org/c-sharp-get-an-enumerator-that-iterates-through-the-sorteddictionary/)

**排序字典< TKey，TValue >。GetEnumerator 方法**用于获取遍历 SortedDictionary < TKey，tvvalue>的枚举器。

**语法:**

> 公共系统。集合。通用。排序字典<tkey tvalue="">。枚举器 GetEnumerator()；</tkey>

**返回值:**这个方法返回一个*排序字典< TKey，TValue >。排序字典< TKey 的枚举器*，TValue >。

以下程序说明了上述方法:

下面的程序说明了上面讨论过的方法:

**例 1:**

```cs
// C# code to get an IDictionaryEnumerator
// that iterates through the SortedDictionary
using System;
using System.Collections;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedDictionary named myDict
        SortedDictionary<string, string> myDict = 
           new SortedDictionary<string, string>();

        myDict.Add("Australia", "Canberra");
        myDict.Add("Belgium", "Brussels");
        myDict.Add("Netherlands", "Amsterdam");
        myDict.Add("China", "Beijing");
        myDict.Add("Russia", "Moscow");
        myDict.Add("India", "New Delhi");

        // To get an IDictionaryEnumerator
        // for the SortedDictionary
        IDictionaryEnumerator myEnumerator = 
                      myDict.GetEnumerator();

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

**例 2:**

```cs
// C# code to get an IDictionaryEnumerator
// that iterates through the SortedDictionary
using System;
using System.Collections;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedDictionary named myDict
        SortedDictionary<string, string> myDict = 
           new SortedDictionary<string, string>();

        // Adding key/value pairs in myDict
        myDict.Add("I", "C");
        myDict.Add("II", "C++");
        myDict.Add("III", "Java");
        myDict.Add("IV", "Python");
        myDict.Add("V", "C#");

        // To get an IDictionaryEnumerator
        // for the Dictionary
        IDictionaryEnumerator myEnumerator = 
                     myDict.GetEnumerator();

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

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . sorted dictionary-2 . get enumerator？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sorteddictionary-2.getenumerator?view=netframework-4.7.2)