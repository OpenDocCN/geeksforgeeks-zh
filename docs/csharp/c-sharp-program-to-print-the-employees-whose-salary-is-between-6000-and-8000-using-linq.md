# 使用 LINQ

打印工资在 6000 到 8000 之间的员工的 C# 程序

> 原文:[https://www . geeksforgeeks . org/c-sharp-program-to-print-the-employees-first-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-print-the-employees-whose-salary-is-between-6000-and-8000-using-linq/)

LINQ 被称为语言集成查询，它是在年引入的。NET 3.5。它赋予*能力。NET* 语言生成查询，从数据源中检索数据。它消除了编程语言和数据库之间的不匹配，并且无论使用哪种类型的数据源，用于创建查询的语法都是相同的。在本文中，我们将使用 LINQ 获取工资在 6000 到 8000 之间的员工详细信息。

**示例:**

```cs
Input:
List of employees:
      {{emp_id = 101, emp_name = "bobby", emp_age = 12, emp_salary = 2000}}
Output:
No Output

Input:
List of employees:
     {{emp_id = 101, emp_name = "bobby",  emp_age = 12, emp_salary = 8900},
      {emp_id = 102, emp_name = "deepu",  emp_age = 15, emp_salary = 7000},
      {emp_id = 103, emp_name = "manoja", emp_age = 13, emp_salary = 6700}}
Output:
      {{emp_id = 102, emp_name = "deepu",  emp_age = 15, emp_salary = 7000},
       {emp_id = 103, emp_name = "manoja", emp_age = 13, emp_salary = 6700}}
```

**进场:**

> 要显示薪资在 6000 到 8000 之间的员工详细信息，请遵循以下方法:
> 
> 1.  创建包含四个变量(身份证、姓名、部门和工资)的员工列表
> 2.  使用 where 函数迭代员工详细信息，并通过选择 6000 到 8000 之间的员工工资来获取员工详细信息。
> 3.  选择介于 6000 和 8000 之间的详细信息
> 4.  调用 ToString 方法
> 5.  显示员工详细信息

**示例:**

## C#

```cs
// C# program to display the details of the employee's
// whose salary is between 6000 and 8000 
// using LINQ.
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

class Employee{

// Declare 4 variables - id,age, name and salary
int emp_id; 
string emp_dept;
string emp_name;
int emp_salary;

// Get the to string method that returns id,
// name, age and salary
public override string ToString()
{
    return emp_id + " " + emp_name + " " + 
           emp_dept + " " + emp_salary;
}

// Driver code
static void Main(string[] args)
{

    // Declare a list variable 
    List<Employee> emp = new List<Employee>()
    {

        // Create 3 employee details
        new Employee{ emp_id = 101, emp_name = "bobby", 
                      emp_dept = "HR", emp_salary = 8900  },
        new Employee{ emp_id = 102, emp_name = "deepu", 
                      emp_dept = "Development", emp_salary = 7000 },
        new Employee{ emp_id = 103, emp_name = "manoja", 
                      emp_dept = "HR", emp_salary = 6700 }};

    // Iterate the Employee by selecting Employee id
    // greater than 101 using where function
    IEnumerable<Employee> Query = 
    from employee in emp where employee.emp_salary >= 6000 &&
    employee.emp_salary <= 8000 select employee;

    // Display employee details
    Console.WriteLine("ID  Name  Department Salary");
    Console.WriteLine("+++++++++++++++++++++++++++");
    foreach (Employee e in Query)
    {

        // Call the to string method
        Console.WriteLine(e.ToString());
    }
}
}
```

**输出:**

```cs
ID  Name  Department Salary
+++++++++++++++++++++++++++
102 deepu Development 7000
103 manoja HR 6700
```