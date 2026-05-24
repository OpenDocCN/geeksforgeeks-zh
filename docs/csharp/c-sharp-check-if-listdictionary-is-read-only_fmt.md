# C# |检查列表字典是否为只读

> 原文：[https://www.geeksforgeeks.org/c-sharp-check-if-listdictionary-is-read-only/](https://www.geeksforgeeks.org/c-sharp-check-if-listdictionary-is-read-only/)

`ListDictionary.IsReadOnly` 属性用于获取一个值，该值指示列表字典是否是只读的。

## 语法：

```cs
public bool IsReadOnly { get; }
```

## 返回值：

该属性始终返回 `false`。

## 例：

```cs
// C# code to check if ListDictionary is read-only
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

        // Checking if ListDictionary is read-only
        Console.WriteLine(myDict.IsReadOnly);
    }
}
```

## 输出：

```cs
False
```

## 注意：

*   只读集合在创建后不允许添加、删除或修改元素。
*   只读集合只是一个带有包装器的集合，该包装器防止集合被修改。因此，如果对基础集合进行了更改，只读集合将反映这些更改。
*   检索此属性的值是一个 `O(1)` 操作。

## 参考：

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.listdictionary.isreadonly?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.listdictionary.isreadonly?view=netframework-4.7.2)