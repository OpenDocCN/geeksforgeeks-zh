# 使用 LINQ

检查所有员工工资低于 10000 的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-check-所有员工的工资低于-10000-using-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-check-the-salary-of-all-employees-is-less-than-10000-using-linq/)

给定员工的数据，现在我们的任务是检查是否所有员工的工资都低于 10000。所以我们用 LINQ 的 All()方法。此方法用于检查源序列中的所有元素是否满足给定的条件。如果给定序列中存在的所有元素都通过测试，则返回 true。否则，它将返回 false。所以解决给定的问题我们使用下面的 LINQ 查询:

> 结果=极客。所有(极客= >极客。Emp _ 薪资<10000；
> 
> T3】

这里， *result* 是一个布尔型变量，用于存储最终结果， *Geeks* 是序列， *All()* 方法用于查找工资低于 10000 的员工列表。

**例:**

```cs
Input: {id = 301, Name = Mohit, Salary = 10000}
       {id = 302, Name = Priya, Salary = 20000}
       {id = 303, Name = Sohan, Salary = 40000}
       {id = 304, Name = Rohit, Salary = 10000}
Output: False

Input: {id = 401, Name = Rohan, Salary = 1000}
       {id = 404, Name = Mohan, Salary = 4000}
Output: True
```

**例 1:**

## C#

```cs
// C# program to determine the salary of all employees
// is less than 10000 
using System;
using System.Linq;
using System.Collections.Generic;

class Geek{

# pragma warning disable 169, 414
int emp_id;
string Emp_Name;
int Emp_Salary;
string Emp_Department;

static void Main(string[] args)
{

    // List of employee details 
    List<Geek> Geeks = new List<Geek>()
    {
        new Geek{emp_id = 401, Emp_Name = "Rajat", Emp_Salary = 50000},
        new Geek{emp_id = 402, Emp_Name = "Ram", Emp_Salary = 65000},
        new Geek{emp_id = 403, Emp_Name = "Krishna", Emp_Salary = 45000},
        new Geek{emp_id = 404, Emp_Name = "Sonial", Emp_Salary = 20000},
        new Geek{emp_id = 405, Emp_Name = "Mickey", Emp_Salary = 70000},
        new Geek{emp_id = 406, Emp_Name = "Kunti", Emp_Salary = 50000},
    };
    bool result;

    // Checking the salary of all employees
    // is less than 10000 
    result = Geeks.All(geek => geek.Emp_Salary < 10000);

    // Display result
    if (result)
    {
        Console.Write("All the salaries are less than 10000");
    }
    else
    {
        Console.Write("All the salaries are not less than 10000");
    }
}
}
```

**Output**

```cs
All the salaries are not less than 10000
```

**例 2:**

## c#

```cs
// C# program to determine the salary of all employees
// is less than 10000 
using System;
using System.Linq;
using System.Collections.Generic;

class Geek{

# pragma warning disable 169, 414
int emp_id;
string Emp_Name;
int Emp_Salary;
string Emp_Department;

static void Main(string[] args)
{

    // List of employee details 
    List<Geek> Geeks = new List<Geek>()
    {
        new Geek{emp_id = 501, Emp_Name = "Rohan", Emp_Salary = 3000},
        new Geek{emp_id = 502, Emp_Name = "Mohan", Emp_Salary = 3000},
        new Geek{emp_id = 503, Emp_Name = "Sham", Emp_Salary = 4000},
        new Geek{emp_id = 504, Emp_Name = "Sonial", Emp_Salary = 1000},
    };
    bool result;

    // Checking the salary of all employees
    // is less than 10000 
    result = Geeks.All(geek => geek.Emp_Salary < 10000);

    // Display the result
    Console.WriteLine("Is the salary of the Geek's employees is < 10000: " + result);
}
}
```

**输出**

```cs
Is the salary of the Geek's employees is < 10000: True
```