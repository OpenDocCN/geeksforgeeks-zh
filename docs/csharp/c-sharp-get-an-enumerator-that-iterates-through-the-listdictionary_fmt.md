# C# 获取遍历 ListDictionary 的枚举器

> 原文：[https://www.geeksforgeeks.org/c-sharp-get-an-enumerator-that-iterates-through-the-listdictionary/](https://www.geeksforgeeks.org/c-sharp-get-an-enumerator-that-iterates-through-the-listdictionary/)

`ListDictionary.GetEnumerator` 方法用于返回一个 `IDictionaryEnumerator`，用于迭代遍历 `ListDictionary`。

## 语法

```cs
public System.Collections.IDictionaryEnumerator GetEnumerator ();
```

## 返回值

此方法为 `ListDictionary` 返回一个 `IDictionaryEnumerator`。

以下程序说明了 `ListDictionary.GetEnumerator` 方法的使用：

### 例 1

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

**输出：**

```cs
Australia --> Canberra
Belgium --> Brussels
Netherlands --> Amsterdam
China --> Beijing
Russia --> Moscow
India --> New Delhi
```

### 例 2

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

**输出：**

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

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.listdictionary.getenumerator?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.listdictionary.getenumerator?view=netframework-4.7.2)