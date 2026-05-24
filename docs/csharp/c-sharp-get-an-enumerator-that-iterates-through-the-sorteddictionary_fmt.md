# C# | 获取遍历 SortedDictionary 的枚举器

> 原文：[`https://www.geeksforgeeks.org/c-sharp-get-an-enumerator-that-iterates-through-the-sorteddictionary/`](https://www.geeksforgeeks.org/c-sharp-get-an-enumerator-that-iterates-through-the-sorteddictionary/)

`SortedDictionary<TKey, TValue>.GetEnumerator` 方法用于获取遍历 `SortedDictionary<TKey, TValue>` 的枚举器。

## 语法

`public System.Collections.Generic.SortedDictionary<TKey, TValue>.Enumerator GetEnumerator();`

## 返回值

此方法返回一个 `SortedDictionary<TKey, TValue>.Enumerator` 枚举器。

以下程序说明了上述方法：

## 例 1

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

## Output

```cs
Australia --> Canberra
Belgium --> Brussels
China --> Beijing
India --> New Delhi
Netherlands --> Amsterdam
Russia --> Moscow
```

## 例 2

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

## Output

```cs
I --> C
II --> C++
III --> Java
IV --> Python
V --> C#
```

## 注

*   C# 语言的 `foreach` 语句隐藏了枚举器的复杂性。因此，建议使用 `foreach`，而不是直接操作枚举器。
*   枚举数可用于读取集合中的数据，但不能用于修改基础集合。
*   `Current` 返回同一对象，直到调用 `MoveNext` 或 `Reset` 为止。`MoveNext` 将 `Current` 设置为下一个元素。
*   只要集合保持不变，枚举数就保持有效。如果对集合进行了更改，例如添加、修改或删除元素，枚举数将无法恢复地失效，并且其行为未定义。
*   这个方法是一个 O(1) 运算。

## 参考

*   [`https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sorteddictionary-2.getenumerator?view=netframework-4.7.2`](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sorteddictionary-2.getenumerator?view=netframework-4.7.2)