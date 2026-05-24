# 使用 LINQ 打印姓名少于 4 个字符的员工的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-print-the-employees-name-包含少于 4 个字符-使用-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-print-the-employees-whose-name-contains-less-than-4-characters-using-linq/)

[LINQ](https://www.geeksforgeeks.org/linq-language-integrated-query/) 被称为语言集成查询，它是在。NET 3.5。它赋予了。NET 语言生成查询以从数据源检索数据。它消除了编程语言和数据库之间的不匹配，并且无论使用哪种类型的数据源，用于创建查询的语法都是相同的。在本文中，我们将研究如何显示那些姓名中包含少于四个字符的员工姓名。所以对于这个任务，我们使用 [Where()](https://www.geeksforgeeks.org/linq-filtering-operator-where/) 函数。这个函数根据给定的条件过滤给定的数组。

**语法:**

```cs
data.Where(employee => employee.Length < 4)
```

**示例:**

```cs
Input : [("m"),("srav"),("a"),("gopi"),("bai")("sai")]
Output : [("m"),("a"),("bai"),("sai")]

Input  : [("bobby"),("ramya"),("sairam")]
Output : No Output
```

**接近**

> 要打印姓名少于 4 个字符的员工列表，请执行以下步骤:
> 
> 1.  创建一个包含员工姓名的列表(例如 XEmployee)。
> 2.  将员工姓名添加到列表中。
> 3.  现在使用数据查找长度小于 4 个字符的员工姓名。其中(员工= >员工。长度< 4)。
> 4.  显示员工姓名。

**示例:**

## C#

```cs
// C# program display those employee's name 
// that contains less than 4 characters in their name
using System;
using System.Collections.Generic;
using System.Linq;

class GFG{

static void Main(string[] args)
{

    // Define a list
    List<string> XEmployee = new List<string>();

    // Add names into the list
    XEmployee.Add("m");
    XEmployee.Add("srav");
    XEmployee.Add("a");
    XEmployee.Add("gopi");
    XEmployee.Add("bai");
    XEmployee.Add("sai");

    // Choose the employee whose name length is
    // less than 4 letters 
    IEnumerable<string> result = XEmployee.Where(
                                 employee => employee.Length < 4);

    Console.WriteLine("Name of the Employees are: ");

    // Display employee names
    foreach (string stname in result)
    {
        Console.WriteLine(stname);
    }
}
}
```

**输出:**

```cs
Name of the Employees are: 
m
a
bai
sai
```