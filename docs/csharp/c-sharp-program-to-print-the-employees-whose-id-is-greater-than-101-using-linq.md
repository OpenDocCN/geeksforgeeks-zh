# 使用 LINQ

打印身份证号大于 101 的员工的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-print-the-employees-id-大于-101-using-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-print-the-employees-whose-id-is-greater-than-101-using-linq/)

LINQ 被称为语言集成查询，它是在年引入的。NET 3.5。它赋予*能力。NET* 语言生成查询，从数据源中检索数据。它消除了编程语言和数据库之间的不匹配，并且无论使用哪种类型的数据源，用于创建查询的语法都是相同的。在本文中，我们将使用 LINQ 显示 ID 大于 101 的员工详细信息。

**示例:**

```cs
Input:
List of employees:
      {{emp_id = 101, emp_name = "bobby",  emp_age = 12},
       {emp_id = 102, emp_name = "deepu",  emp_age = 15},
       {emp_id = 103, emp_name = "manoja", emp_age = 13},
       {emp_id = 104, emp_name = "saroja", emp_age = 14},
       {emp_id = 105, emp_name = "sravan", emp_age = 15},
       {emp_id = 106, emp_name = "navya",  emp_age = 12},
       {emp_id = 107, emp_name = "majnu",  emp_age = 12},
       {emp_id = 108, emp_name = "vishnu", emp_age = 12}}
Output:
      {{emp_id = 102, emp_name = "deepu",  emp_age = 15},
       {emp_id = 103, emp_name = "manoja", emp_age = 13},
       {emp_id = 104, emp_name = "saroja", emp_age = 14},
       {emp_id = 105, emp_name = "sravan", emp_age = 15},
       {emp_id = 106, emp_name = "navya",  emp_age = 12},
       {emp_id = 107, emp_name = "majnu",  emp_age = 12},
       {emp_id = 108, emp_name = "vishnu", emp_age = 12}}

Input:
List of employees:
      {{emp_id = 101, emp_name = "bobby",  emp_age = 12},
       {emp_id = 102, emp_name = "deepu",  emp_age = 15},
       {emp_id = 103, emp_name = "manoja", emp_age = 13}}
Output:
      {{emp_id = 102, emp_name = "deepu",  emp_age = 15},
       {emp_id = 103, emp_name = "manoja", emp_age = 13}}
```

**进场:**

> 要显示 ID 大于 101 的员工详细信息，请遵循以下方法:
> 
> 1.  创建包含三个变量(身份证、姓名和年龄)的员工列表
> 2.  使用 where 函数迭代员工详细信息，并通过选择大于 101 的员工 id 来获取员工详细信息
> 3.  选择大于 101 的详细信息
> 4.  调用 ToString()方法
> 5.  显示员工详细信息

**示例:**

## C#

```cs
// C# program to display the details of the employee
// whose ID greater than 101 
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

public class Employee{

// Declare 3 variables - id,age and name
int emp_id; 
int emp_age;
string emp_name;

// Get the to string method that returns
// id , name and age
public override string ToString()
{
    return emp_id + " " + emp_name + " " + emp_age;
}

// Driver code
static void Main(string[] args)
{

    // Declare a list variable 
    List<Employee> emp1 = new List<Employee>()
    {

        // Create 8 employee details
        new Employee{ emp_id = 101, emp_name = "bobby", emp_age = 12},
        new Employee{ emp_id = 102, emp_name = "deepu", emp_age = 15},
        new Employee{ emp_id = 103, emp_name = "manoja", emp_age = 13},
        new Employee{ emp_id = 104, emp_name = "saroja", emp_age = 14},
        new Employee{ emp_id = 105, emp_name = "sravan", emp_age = 15},
        new Employee{ emp_id = 106, emp_name = "navya", emp_age = 12},
        new Employee{ emp_id = 107, emp_name = "majnu", emp_age = 12},
        new Employee{ emp_id = 108, emp_name = "vishnu", emp_age = 12},
    };

    // Iterate the Employee by selecting Employee
    // id greater than 101
    // Using where clause
    IEnumerable<Employee> Query = 
    from employee in emp1 where employee.emp_id > 101 select employee;

    // Display employee details
    Console.WriteLine("ID  Name  Age");
    Console.WriteLine("+++++++++++++");
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
ID  Name  Age
+++++++++++++
102 deepu 15
103 manoja 13
104 saroja 14
105 sravan 15
106 navya 12
107 majnu 12
108 vishnu 12
```