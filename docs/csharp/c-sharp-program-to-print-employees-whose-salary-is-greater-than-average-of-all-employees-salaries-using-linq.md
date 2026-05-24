# 使用 LINQ 打印工资高于所有员工平均工资的员工的 C# 程序

> 原文:[https://www . geeksforgeeks . org/c-sharp-program-to-print-工资高于所有员工平均工资的员工-使用-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-print-employees-whose-salary-is-greater-than-average-of-all-employees-salaries-using-linq/)

LINQ 被称为语言集成查询，它是在年引入的。NET 3.5。它赋予了。NET 语言生成查询以从数据源检索数据。它消除了编程语言和数据库之间的不匹配，并且无论使用哪种类型的数据源，用于创建查询的语法都是相同的。在本文中，我们将学习如何显示工资高于所有员工平均工资的员工详细信息列表。

**例:**

```cs
Input:
{{emp_Name = "sravan", emp_Age = 21, emp_Salary = 26199},
 {emp_Name = "ramya", emp_Age = 22, emp_Salary = 19000},
 {emp_Name = "harsha", emp_Age = 23, emp_Salary = 25000},
 {emp_Name = "deepu", emp_Age = 23, emp_Salary = 23456},
 {emp_Name = "jyothika", emp_Age = 21, emp_Salary = 21345}}
Output:
 {emp_Name = "sravan", emp_Age = 21, emp_Salary = 26199}
 {emp_Name = "harsha", emp_Age = 23, emp_Salary = 25000}
 {emp_Name = "deepu", emp_Age = 23, emp_Salary = 23456}

Input:
{{emp_Name = "sravan", emp_Age = 21, emp_Salary = 26199},
 {emp_Name = "ramya", emp_Age = 22, emp_Salary = 19000}}
Output:
{emp_Name = "sravan", emp_Age = 21, emp_Salary = 26199}
```

**方法:**

> 1.  声明三个变量——员工姓名、年龄和工资
> 2.  使用列表集创建员工列表。
> 3.  使用查询计算所有员工的平均工资。
> 4.  使用 where 子句检查每个员工的哪个工资高于平均值。
> 5.  选择员工。
> 6.  使用 ToString()方法显示结果。

**例:**

## c#

```cs
// C# program to display the lits of employees 
// whose salary is greater than average salary 
// of all the employees
using System;
using System.Collections.Generic;
using System.Linq;

class Employee{

// Declare three variables
// employee name, age, and Salary
string emp_Name;
int emp_Age;
int emp_Salary;

// Get the data
public override string ToString()
{
    return " " + emp_Name + " " + 
                  emp_Age + " " + emp_Salary;
}

// Driver code
static void Main(string[] args)
{

    // Create the list of 5 employees
    List<Employee> emp = new List<Employee>()
    {
        new Employee{ emp_Name = "sravan", emp_Age = 21, 
                      emp_Salary = 26199 },
        new Employee{ emp_Name = "ramya", emp_Age = 22, 
                      emp_Salary = 19000 },
        new Employee{ emp_Name = "harsha", emp_Age = 23, 
                      emp_Salary = 25000 },
        new Employee{ emp_Name = "deepu", emp_Age = 23, 
                      emp_Salary = 23456 },
        new Employee{ emp_Name = "jyothika", emp_Age = 21, 
                      emp_Salary = 21345 }
    };

    IEnumerable<Employee> result =

    // Getting the average of all the employees
    from e in emp

    // Total
    let total = emp.Sum(sal => sal.emp_Salary)
    let average = total / 5

    // Condition to get salary greater than 
    // average of all employees
    where e.emp_Salary > average

    // Select that employees
    select e;

    Console.WriteLine(" Employee-Name Employee-Age Employee-Salary");
    foreach (Employee x in result)
    {
        Console.WriteLine(x.ToString());
    }
}
}
```

**输出:**

```cs
Employee-Name Employee-Age Employee-Salary
sravan 21 26199
harsha 23 25000
deepu 23 23456
```