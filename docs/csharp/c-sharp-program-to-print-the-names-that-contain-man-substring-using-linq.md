# 使用 LINQ 打印包含“MAN”子串的名称的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-print-the-name-contain-man-substring-use-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-print-the-names-that-contain-man-substring-using-linq/)

[LINQ](https://www.geeksforgeeks.org/linq-language-integrated-query/) 被称为语言集成查询，它是在。NET 3.5。它赋予了。NET 语言生成查询以从数据源检索数据。它消除了编程语言和数据库之间的不匹配，并且无论使用哪种类型的数据源，用于创建查询的语法都是相同的。在本文中，我们将学习如何使用 LINQ 打印给定数组中包含“MAN”子串的那些名称。所以为了完成我们的任务，我们使用了[中的](https://www.geeksforgeeks.org/linq-filtering-operator-where/)[包含()](https://www.geeksforgeeks.org/linq-quantifier-operator-contains/)方法和方法。

**语法:**

```cs
Where(employee => employee.Contains("MAN"))
```

这里，Contains()方法用于检查给定的字符串中是否包含“MAN”字，然后 Where()方法相应地过滤数组。

**示例:**

```cs
Input  : [("MANVITHA"),("SRIMANTH"),("RAVI"),("MANASA"),("MOUNIKA")("MANAS");]
Output : [("MANVITHA"),("SRIMANTH"),("MANASA"),("MANAS")]

Input  : [("bobby"),("ramya"),("sairam");]
Output : No Output
```

**接近**

> 要打印包含“MAN”作为子字符串的名称列表，请执行以下步骤:
> 
> 1.  创建一个包含员工姓名的列表(例如 XEmployee)。
> 2.  将这些名字添加到列表中。
> 3.  现在，使用 XEmployee 查找其名称包含“MAN”作为子字符串的名称。其中(员工= >员工。包含(“人”))
> 4.  显示员工姓名。

**示例:**

## C#

```cs
// C# program to display those names that
// contain 'MAN' substring
using System;
using System.Collections.Generic;
using System.Linq;

class GFG{

static void Main(string[] args)
{

    // Define a list
    List<string> XEmployee = new List<string>();

    // Add names into the list
    XEmployee.Add("MANVITHA");
    XEmployee.Add("SRIMANTH");
    XEmployee.Add("RAVI");
    XEmployee.Add("MANASA");
    XEmployee.Add("MOUNIKA");
    XEmployee.Add("MANAS");

    // Choose the employee's name that
    // contains MAN as a sub string
    IEnumerable<string> final = XEmployee.Where(
                                employee => employee.Contains("MAN"));

    Console.WriteLine("Names that conatin MAN substring:");

    // Display employee names
    foreach (string stname in final)
    {
        Console.WriteLine(stname);
    }
}
}
```

**输出:**

```cs
Names that conatin MAN substring:
MANVITHA
SRIMANTH
MANASA
MANAS
```