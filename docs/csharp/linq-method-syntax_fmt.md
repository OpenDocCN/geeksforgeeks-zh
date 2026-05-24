# LINQ 方法语法

> 原文: [https://www.geeksforgeeks.org/linq-method-syntax/](https://www.geeksforgeeks.org/linq-method-syntax/)

在 LINQ 中，方法语法用于调用 `Enumerable` 或 `Queryable` 静态类的扩展方法。也称为方法扩展语法或流利语法。但是，编译器总是在编译时将查询语法转换为方法语法。它可以调用标准的查询操作符，如 `Select`、`Where`、`GroupBy`、`Join`、`Max` 等。您可以不使用查询语法直接调用它们。

## 使用 C# 中的方法语法创建第一个 LINQ 查询

### 步骤 1: 添加命名空间

首先在代码中添加 `System.Linq` 命名空间。

```cs
using System.Linq;
```

### 步骤 2: 创建数据源

接下来，创建一个用于操作的数据源。例如：

```cs
List<string> my_list = new List<string>(){
    "This is my Dog",
    "Name of my Dog is Robin",
    "This is my Cat",
    "Name of the cat is Mewmew"
};
```

### 步骤 3: 创建查询

现在使用 `Enumerable` 或 `Queryable` 静态类提供的方法创建查询。例如：

```cs
var res = my_list.Where(a => a.Contains("Dog"));
```

这里 `res` 是存储查询表达式结果的查询变量。在这里，我们找到了包含“Dog”的字符串。因此，我们使用 `Where()` 方法根据方法中给出的 lambda 表达式 `a => a.Contains("Dog")` 过滤数据源。

### 步骤 4: 执行查询

最后一步是使用 `foreach` 循环执行查询。例如：

```cs
foreach(var q in res)
{
    Console.WriteLine(q);
}
```

## 示例

```cs
// Create the first Query in C# using Method Syntax
using System;
using System.Linq;
using System.Collections.Generic;

class GFG {

    // Main Method
    static public void Main()
    {
        // Data source
        List<string> my_list = new List<string>() {
            "This is my Dog",
            "Name of my Dog is Robin",
            "This is my Cat",
            "Name of the cat is Mewmew"
        };

        // Creating LINQ Query
        // Using Method syntax
        var res = my_list.Where(a => a.Contains("Dog"));

        // Executing LINQ Query
        foreach(var q in res)
        {
            Console.WriteLine(q);
        }
    }
}
```

## 输出

```cs
This is my Dog
Name of my Dog is Robin
```