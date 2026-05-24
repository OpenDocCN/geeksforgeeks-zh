# LINQ |查询语法

> 原文:[https://www.geeksforgeeks.org/linq-query-syntax/](https://www.geeksforgeeks.org/linq-query-syntax/)

LINQ 查询语法是由一组定义到*中的查询关键词组成的。NET Framework 版或更高版本*。这允许程序员或开发人员在代码中编写类似于 SQL 风格的命令(C# 或 VB.NET)，而无需使用引号。它也被称为**查询表达式语法**。在 [LINQ](https://www.geeksforgeeks.org/linq-language-integrated-query/) 中，您可以使用以下方式将查询写入 IEnumerable 集合或 IQueryable 数据源:

1.  **查询语法**
2.  **方法语法**

这里，我们将只讨论查询语法。

#### 查询语法

LINQ 查询语法以关键字中的*开始，以*选择*或*分组*关键字结束。在*之后，从*关键字可以使用不同类型的标准查询操作，如过滤、分组等。根据你的需要。在 LINQ，有 50 种不同类型的标准查询运算符可用。*

**使用 C# 中的查询语法创建第一个 LINQ 查询**

*   **第一步:**先添加*系统。Linq* 命名空间在你的代码中。

    ```cs
    using System.Linq;
    ```

*   **步骤 2:** 接下来，创建要对其执行操作的数据源。例如:

    ```cs
    List my_list = new List(){
            "This is my Dog",
            "Name of my Dog is Robin",
            "This is my Cat",
            "Name of the cat is Mewmew"
        };

    ```

*   **Step 3:** Now create the query using the query keywords like select, from, etc. For example:

    ```cs

    var res = from l in my_list
                  where l.Contains("my")
                  select l;

    ```

    这里 *res* 是存储查询表达式结果的查询变量。来自子句的*用于指定数据源，即 *my_list* ，其中子句应用过滤器，即 l.Contains(“我的”)，select 子句提供返回项目的类型。l 是范围变量。*

*   **步骤 4:** 最后一步是使用 foreach 循环执行查询。例如:

    ```cs
    foreach(var q in res)
    {
             Console.WriteLine(q);
    }

    ```

**示例:**

```cs
// Create first Query in C#
using System;
using System.Linq;
using System.Collections.Generic;

class GFG {

    // Main Method
    static public void Main()
    {

        // Data source
        List<string> my_list = new List<string>() 
        {
                "This is my Dog",
                "Name of my Dog is Robin",
                "This is my Cat",
                "Name of the cat is Mewmew"
        };

        // Creating LINQ Query
        var res = from l in my_list
                  where l.Contains("my")
                  select l;

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
This is my Cat

```