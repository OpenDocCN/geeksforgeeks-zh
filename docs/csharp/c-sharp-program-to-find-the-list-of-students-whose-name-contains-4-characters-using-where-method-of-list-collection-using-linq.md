# 使用 LINQ 列表收集的 Where()方法查找姓名包含 4 个字符的学生列表的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-find-the-list-list-collection-use-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-find-the-list-of-students-whose-name-contains-4-characters-using-where-method-of-list-collection-using-linq/)

LINQ 被称为语言集成查询，它是在年引入的。NET 3.5。它赋予了。NET 语言生成查询以从数据源检索数据。它消除了编程语言和数据库之间的不匹配，并且无论使用哪种类型的数据源，用于创建查询的语法都是相同的。在本文中，我们将学习如何使用 LINQ 的 Where()子句打印姓名包含 4 个字符的学生列表。所以要使用 Where()子句，您需要添加 System。临朐与系统。集合。程序中的通用命名空间。

**语法:**

> 数据。其中(学生= >学生。长度== 4)

**示例:**

```cs
Input  : [("bobby"),("srav"),("ramya"),("gopi"),("hari")("sai");]
Output : [("srav"),("gopi"),("hari")]
Input  : [("bobby"),("ramya"),("sai");]
Output : No Output
```

**接近**

> 要打印姓名包含 4 个字符的学生列表，请执行以下步骤:
> 
> 1.  创建列表
> 2.  将学生姓名添加到列表中
> 3.  用数据找出长度为 4 的学生名字。其中(学生= >学生。长度== 4)
> 4.  显示学生姓名

**示例:**

## C#

```cs
// C# program to display the list of students whose 
// name contains four characters using Where() method 
using System;
using System.Collections.Generic;
using System.Linq;

class GFG{

static void Main(string[] args)
{

    // Define a list
    List<string> data = new List<string>();

    // Add names into the list
    data.Add("bobby");
    data.Add("srav");
    data.Add("ramya");
    data.Add("gopi");
    data.Add("hari");
    data.Add("sai");

    // Choose the student whose name length is 4 
    // Using where clause
    IEnumerable<string> final = data.Where(student => student.Length == 4);

    Console.WriteLine("Length 4 Details");

    // Display student names
    foreach (string stname in final)
    {
        Console.WriteLine(stname);
    }
}
}
```

**输出:**

```cs
Length 4 Details
srav
gopi
hari
```