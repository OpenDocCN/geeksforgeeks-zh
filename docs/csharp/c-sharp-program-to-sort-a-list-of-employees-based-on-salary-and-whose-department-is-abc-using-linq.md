# C# 程序，使用 LINQ

根据工资和 ABC 是谁的部门对员工列表进行排序

> 原文:[https://www . geeksforgeeks . org/c-sharp-program-to-sort-a-list-employees-based-on-pay-and-who-department-ABC-using-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-sort-a-list-of-employees-based-on-salary-and-whose-department-is-abc-using-linq/)

给定一个员工列表，现在我们的任务是根据工资对给定的员工列表进行排序，并使用 LINQ 对 ABC 是谁的部门进行排序。

**示例:**

```cs
Input: 
{id = 101, name = "Sumit", salary = 10000, department = ABC} 
{id = 102, name = "Rohit", salary = 20000, department = HR} 
{id = 103, name = "Mohit", salary = 30000, department = ABC} 
{id = 104, name = "Sunil", salary = 40000, department = ABC} 
Output:
{id = 101, name = "Sumit", salary = 10000, department = ABC} 
{id = 103, name = "Mohit", salary = 30000, department = ABC} 
{id = 104, name = "Sunil", salary = 40000, department = ABC} 
```

**进场:**

**1。**创建包含身份证、姓名、工资和部门的员工列表

**2。**使用 OrderBy()方法和 Where()方法根据工资和 ABC 部门对员工列表进行排序

```cs
var result_set = Geeks.Where(emp => emp.Emp_Department == "ABC").OrderBy( 
                            sal  =>  sal.Emp_Salary);
```

**3。**显示排序列表

**示例:**

## C#

```cs
// C# program to display a sorted list of employees based 
// on Salary and whose Department is ABC 
using System;
using System.Linq;
using System.Collections.Generic;

public class Geek{

int emp_id;
string Emp_Name;
int Emp_Salary;
string Emp_Department;

// Driver code
static void Main(string[] args)
{

    // Geeks data
    List<Geek> Geeks = new List<Geek>()
    {
        new Geek{emp_id = 101, Emp_Name = "arjun", 
                 Emp_Salary = 50000, Emp_Department = "ABC"},
        new Geek{emp_id = 102, Emp_Name = "bheem", 
                 Emp_Salary = 65000, Emp_Department = "DEF"},
        new Geek{emp_id = 103, Emp_Name = "krishna", 
                 Emp_Salary = 45000, Emp_Department = "ABC"},
        new Geek{emp_id = 104, Emp_Name = "Ram", 
                 Emp_Salary = 20000, Emp_Department = "DEF"},
        new Geek{emp_id = 105, Emp_Name = "kiran", 
                 Emp_Salary = 70000, Emp_Department = "DEF"},
        new Geek{emp_id = 106, Emp_Name = "karna", 
                 Emp_Salary = 50000, Emp_Department = "ABC"},
    };

    // Using the where command we have selected the geeks
    // having ABC department and then we have sorted the
    // data using OrderBy() command
    var result_set = Geeks.Where(emp => emp.Emp_Department == "ABC").OrderBy(
                                 sal => sal.Emp_Salary);

    foreach (Geek emp in result_set)
    {
        Console.WriteLine(emp.emp_id + " " + 
                          emp.Emp_Name +" " + 
                          emp.Emp_Salary + " " + 
                          emp.Emp_Department);
    }
}
}
```

**Output**

```cs
103 krishna 45000 ABC
101 arjun   50000 ABC
106 karna 50000 ABC
```