# 用 `StringComparer` 演示 LINQ `Union()` 方法示例的 C# 程序

> 原文：[https://www.geeksforgeeks.org/c-sharp-program-to-demonstrate-the-example-of-linq-union-method-with-stringcomparer/](https://www.geeksforgeeks.org/c-sharp-program-to-demonstrate-the-example-of-linq-union-method-with-stringcomparer/)

## 介绍
LINQ 被称为语言集成查询，它是在 .NET 3.5 中引入的。它给了 .NET 语言创建查询以从数据源检索数据。在本文中，我们将使用 `StringComparer` 演示 LINQ `Union()` 方法的示例。

## `Union()` 方法
`Union()` 方法用于从给定列表中获取唯一元素。或者我们可以说这个方法返回两个列表的并集。该函数将两个列表作为输入，然后在重复元素中只获取一次元素。

### 语法
```cs
data1.Union(data2)
```
其中 `data1` 是第一个列表，`data2` 是第二个列表。

## `StringComparer`
它是一个用于比较使用特定大小写或序数比较规则的字符串的类。我们可以在 `Union()` 函数中使用这个 `StringComparer` 来获取带有 string（区分大小写）的元素。它将比较两个列表中的字符串并返回字符串。

### 语法
```cs
StringComparer.OrdinalIgnoreCase
```
如果我们使用 `union()` 函数和 `StringComparer`，那么我们必须首先使用 `Union()` 函数，然后使用给定的语法应用 `stringcomparer` 函数。

### 语法
```cs
data1.Union(data2, StringComparer.OrdinalIgnoreCase);
```
其中 `data1` 是第二个列表，`data2` 是第二个列表。

## 示例
```cs
Input: { "Hello", "Geeks", "For", "Geeks" };
       { "Hello", "geeks" , "python" }
Output:
Hello 
Geeks 
For 
python

Input: { "Hello", "Geeks" }
       { "Hello", "geeks" , "python" };
Output:
Hello 
Geeks 
python
```

## 进场
1.  创建两个名为 `data1` 和 `data2` 的字符串类型列表。
2.  使用字符串比较器执行联合操作
    ```cs
    data1.Union(data2, StringComparer.OrdinalIgnoreCase);
    ```
3.  使用 `foreach` 循环显示结果
    ```cs
    foreach(var j in final)
    {
        Console.WriteLine(j + " ");
    }
    ```

## C# 示例
```cs
// C# program to illustrate how to use
// Union() Method with StringComparer in LINQ
using System;
using System.Linq;
using System.Collections.Generic;

class GFG{

static void Main(string[] args)
{

// Create first list with 4 elements
    List<string> data1 = new List<string>(){
        "Hello", "Geeks", "For", "Geeks" };

// Create first list with 3 elements
    List<string> data2 = new List<string>(){
        "Hello", "geeks", "python" };

// Perform union operation
    var final = data1.Union(data2,
                            StringComparer.OrdinalIgnoreCase);

// Display the result
    foreach(var j in final)
    {
        Console.WriteLine(j + " ");
    }
}
}
```

## 输出
```cs
Hello 
Geeks 
For 
python 
```