# C# 程序，演示在 LINQ 使用该方法作为条件

> 原文:[https://www . geeksforgeeks . org/c-sharp-program-to-演示-使用-方法-作为-条件-在-linq-where-method-of-list-collection/](https://www.geeksforgeeks.org/c-sharp-program-to-demonstrate-the-use-of-the-method-as-a-condition-in-the-linq-where-method-of-list-collection/)

[LINQ](https://www.geeksforgeeks.org/linq-language-integrated-query/) 被称为语言集成查询，它是在。NET 3.5。它赋予了。NET 语言生成查询以从数据源检索数据。它消除了编程语言和数据库之间的不匹配，并且无论使用哪种类型的数据源，用于创建查询的语法都是相同的。在本文中，我们将通过雇员数据的示例来演示如何使用方法作为条件，在该示例中，雇员的姓名中包含少于四个字符。所以对于这个任务，我们使用 [Where()](https://www.geeksforgeeks.org/linq-filtering-operator-where/) 函数。这个函数根据给定的条件过滤给定的数组。或者我们可以说，Where()方法根据指定的条件从序列中返回值。

**示例:**

```cs
Input : [("m"), ("srav"), ("a"), ("gopi"), ("bai")("sai")]
Output : [("m"), ("a"), ("bai"), ("sai")]

Input  : [("bobby"), ("ramya"), ("sairam")]
Output : No Output
```

**接近**

> 要打印姓名少于 4 个字符的员工列表，请执行以下步骤:
> 
> 1.  创建一个名为“checkstring”的函数，检查字符串长度是否少于 4 个字符，即字符串。长度< 4。
> 2.  创建一个包含员工姓名的列表(例如 XEmployee)。
> 3.  将员工姓名添加到列表中。
> 4.  现在使用“数据”查找长度小于 4 个字符的员工姓名。其中(员工= >检查字符串(员工))”。
> 5.  显示员工姓名。

**示例:**

## C#

```cs
// C# program to illustrate the use of
// the method as a condition in the 
// LINQ where() method of the list collection
using System;
using System.Collections.Generic;
using System.Linq;

class GFG{

// Function to check the given string is less than 4
static bool checkstring(string str)
{
    if (str.Length < 4)
        return true;
    else
        return false;
}

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
                                 employee => checkstring(employee));

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