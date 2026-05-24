# 使用 LINQ 打印姓氏为“n”的员工的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-print-the-employees-of-name-n-use-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-print-the-employees-whose-last-character-of-name-is-n-using-linq/)

LINQ 被称为语言集成查询，它是在年引入的。NET 3.5。它赋予了。NET 语言生成查询以从数据源检索数据。它消除了编程语言和数据库之间的不匹配，并且无论使用哪种类型的数据源，用于创建查询的语法都是相同的。在本文中，我们将研究如何使用 LINQ 打印姓氏为“n”的员工姓名列表。

**示例:**

```cs
Input : List of Employees:
       {{id = 101, name = "Sravan", age = 12},
        {id = 102, name = "deepu",  age = 15},
        {id = 103, name = "manoja", age = 13},
        {id = 104, name = "Sathwik", age = 12},
        {id = 105, name = "Saran",  age = 15}}
Output: {{id = 105, name = "sravan", age = 15},
        {id = 105, name = "Saran",  age = 15}}

Input: List of Employees:
      {{id = 102, name = "deepu",  age = 15},
       {id = 103, name = "manoja", age = 13}}
Output: No Output
```

**进场:**

> 要查找姓名以“n”字符结尾的员工列表，请执行以下步骤:
> 
> *   创建包含四个变量(身份证、姓名、部门和团队)的员工列表。
> *   使用以下查询，通过选择以“n”结尾的员工姓名，循环查看员工详细信息并获取员工详细信息:
> 
> ```cs
> IEnumerable<Employee> Query = from emp in employees
>                               where emp.name[emp.name.Length - 1] == 'n'
>                               select emp;
> ```
> 
> *   现在调用 ToString()方法。
> *   显示员工详细信息。

**示例:**

## C#

```cs
// C# program to display the list of employees
// whose last character of the name is 'n' 
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

// Create a class with four variables
// employee id, name, and department
class Employee{

int id;
string name;
string department;

// To string method
public override string ToString()
{
    return id + " " + name + " " + department;
}

// Driver code
static void Main(string[] args)
{

    // Create list of employees with 5 data
    List<Employee> emp = new List<Employee>()
    {
        new Employee{ id = 101, name = "Sravan", 
                      department = "Development" },
        new Employee{ id = 102, name = "deepu",  
                      department = "HR" },
        new Employee{ id = 103, name = "manoja", 
                      department = "Development" },
        new Employee{ id = 104, name = "Sathwik", 
                      department = "Development" },
        new Employee{ id = 105, name = "Saran", 
                      department = "HR" }
    };

    // Condition to get employee name ends with 'n'
    IEnumerable<Employee> result = from e in emp
                                   where e.name[e.name.Length - 1] == 'n'
                                   select e;

    Console.WriteLine("ID  Name  Department");
    Console.WriteLine("++++++++++++++++++++");

    // Iterating the employee data to display 
    // By calling the to string method
    foreach (Employee x in result)
    {
        Console.WriteLine(x.ToString());
    }
}
}
```

**输出:**

```cs
ID  Name  Department
++++++++++++++++++++
101 Sravan Development
105 Saran HR
```