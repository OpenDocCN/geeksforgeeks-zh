# C# 检查列表字典是否包含特定的键

> 原文: [https://www.geeksforgeeks.org/c-sharp-check-if-listdictionary-contains-a-specific-key/](https://www.geeksforgeeks.org/c-sharp-check-if-listdictionary-contains-a-specific-key/)

`ListDictionary.Contains(Object)` 方法用于检查列表字典是否包含特定的键。

## 语法

```cs
public bool Contains (object key);
```

这里，`key` 是在列表字典中定位的键。

## 返回值

如果 `ListDictionary` 包含具有指定键的条目，则该方法返回 `true`，否则返回 `false`。

## 异常

如果 `key` 为 `null`，该方法将给出 `ArgumentNullException`。

下面给出了一些例子，以便更好地理解实现。

## 例 1

```cs
// C# code to check if ListDictionary
// contains a specific key
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

        // Checking if ListDictionary contains
        // the key "Brazil"
        Console.WriteLine(myDict.Contains("Brazil"));
    }
}
```

## 输出

```cs
False
```

## 例 2

```cs
// C# code to check if ListDictionary
// contains a specific key
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

        // Checking if ListDictionary contains
        // the key "null". This should raise
        // "ArgumentNullException" as the key is null
        Console.WriteLine(myDict.Contains(null));
    }
}
```

## 运行时错误

> 未处理异常:
> System.ArgumentNullException: 键不能为空。
> 参数名称: key

## 注

此方法为 O(n) 运算，其中 n 为 `Count`。

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.listdictionary.contains?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.listdictionary.contains?view=netframework-4.7.2)