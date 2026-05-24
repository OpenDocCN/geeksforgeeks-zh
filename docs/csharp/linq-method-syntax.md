# LINQ |方法语法

> 原文:[https://www.geeksforgeeks.org/linq-method-syntax/](https://www.geeksforgeeks.org/linq-method-syntax/)

在 LINQ，方法语法用于调用可枚举或可查询静态类的扩展方法。也称为**方法扩展语法**或**流利**。但是，编译器总是在编译时将查询语法转换为方法语法。它可以调用标准的查询操作符，如选择、位置、分组、连接、最大值等。您可以不使用查询语法直接调用它们。

**使用 C# 中的方法语法创建第一个 LINQ 查询**

*   **Step 1:** First add the system. The Linq namespace in the code.

    ```cs
    using System.Linq;
    ```

*   **Step 2:** Next, create a data source to perform the operation. Example:

    ```cs
    List my_list = new List(){
            "This is my Dog",
            "Name of my Dog is Robin",
            "This is my Cat",
            "Name of the cat is Mewmew"
        };

    ```

*   **步骤 3:** 现在使用可枚举或可查询静态类提供的方法创建查询。例如:

    ```cs

    var res = my_list.Where(a=> a.Contains("Dog"));

    ```

    这里 *res* 是存储查询表达式结果的查询变量。在这里，我们找到了包含“狗”的字符串。因此，我们使用 Where()方法根据方法中给出的 lambda 表达式过滤数据源，即 a =>a . Contains(“Dog”)。

*   **Step 4:** The last step is to use the foreach loop to execute the query. Example:

    ```cs
    foreach(var q in res)
    {
             Console.WriteLine(q);
    }

    ```

**例:**

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

**输出:**

```cs
This is my Dog
Name of my Dog is Robin

```