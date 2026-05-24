# SortedList.ContainsKey 方法详解（C# 示例）

> 原文：[https://www.geeksforgeeks.org/sortedlist-containskey-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/sortedlist-containskey-method-in-c-sharp-with-examples/)

给定一个 `SortedList` 对象，我们的任务是检查该对象是否包含特定的键。为此，我们可以使用 `ContainsKey()` 方法。此方法用于确定 `SortedList` 对象是否包含特定的键。如果找到该键，它将返回 `true`，否则返回 `false`。

## 语法

```cs
bool SortedList.ContainsKey(object key);
```

此方法接受一个参数 `key`，即要在排序列表对象中查找的键。

## 示例

```cs
Input  : [(1, "Python"), (2, "c")]
Key    : 1
Output : Found
Input  : [(1, "Python"), (2, "c")]
Key    : 4
Output : Not Found
```

## 实现步骤

1.  创建一个 `SortedList`。
2.  向该排序列表添加键和值。
3.  使用 `ContainsKey()` 方法检查列表中是否存在特定的键。
4.  显示输出结果。

## C# 代码示例

```cs
// C# program to check whether a SortedList 
// object contains a specific key or not
using System;
using System.Collections;

class GFG{

    static public void Main()
    {

        // Create sorted list
        SortedList data = new SortedList();

        // Add elements to data sorted list 
        data.Add(1, "Python");
        data.Add(2, "c");
        data.Add(3, "java");
        data.Add(4, "php");
        data.Add(5, "html");
        data.Add(6, "bigdata");
        data.Add(7, "java script");

        // Check whether the key - 1 is present
        // in the list or not
        if (data.ContainsKey(1))
            Console.WriteLine("Present in the List");
        else
            Console.WriteLine("Not in the List");

        // Check whether the key - 4 is present
        // in the list or not
        if (data.ContainsKey(4))
            Console.WriteLine("Present in the List");
        else
            Console.WriteLine("Not in the List");

        // Check whether the key - 8 is present
        // in the list or not
        if (data.ContainsKey(8))
            Console.WriteLine("Present in the List");
        else
            Console.WriteLine("Not in the List");
    }
}
```

## 输出

```cs
Present in the List
Present in the List
Not in the List
```