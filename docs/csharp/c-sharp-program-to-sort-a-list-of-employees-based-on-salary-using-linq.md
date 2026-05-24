# 使用 LINQ

根据工资对员工列表进行排序的 C# 程序

> 原文:[https://www . geeksforgeeks . org/c-sharp-program-to-sort-a-list-employees-based-on-pay-use-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-sort-a-list-of-employees-based-on-salary-using-linq/)

给定一个员工列表，现在我们使用 LINQ 根据他们的工资对员工列表进行排序。所以对于这个任务，我们使用 [OrderBy()](https://www.geeksforgeeks.org/linq-sorting-operator-orderby/) 方法。此方法用于按升序对指定序列的元素进行排序。

**例:**

```cs
Input: 
{id = 101, Name = Rohit, Salary = 50000, Department = HR}
{id = 104, Name = Rohit, Salary = 10000, Department = Development}
{id = 106, Name = Rohit, Salary = 80000, Department = HR}
{id = 108, Name = Rohit, Salary = 20000, Department = Development}
Output:
{id = 104, Name = Rohit, Salary = 10000, Department = Development}
{id = 108, Name = Rohit, Salary = 20000, Department = Development} 
{id = 101, Name = Rohit, Salary = 50000, Department = HR}
{id = 106, Name = Rohit, Salary = 80000, Department = HR}
```

**进场:**

**1。**创建员工列表以及他们的身份证、姓名、工资和部门。

**2。**现在使用 OrderBy()方法根据员工的工资对员工列表进行排序。

```cs
var result_set = Geeks.OrderBy(sal => sal.Emp_Salary);
```

或者我们也可以使用 LINQ 的 OrderBy 子句

```cs
var result_set = from emp in Geeks orderby emp.Emp_Salary select emp;
```

对列表进行排序

**3。**使用 foreach 循环显示排序列表。

**例 1:**

## c#

```cs
// C# program to sort a list of employees
// based on salary. Using OrderBy() method
using System;
using System.Linq;
using System.Collections.Generic;

class Geek{

int emp_id;
string Emp_Name;
int Emp_Salary;
string Emp_Department;

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

    // We have sorted the data using OrderBy() command
    var result_set = Geeks.OrderBy(sal => sal.Emp_Salary);

    // Display the sorted result
    foreach (Geek emp in result_set)
    {
        Console.WriteLine(emp.emp_id + " " + 
                          emp.Emp_Name + " " + 
                          emp.Emp_Salary + " " + 
                          emp.Emp_Department);
    }
}
}
```

**输出**

```cs
104 Ram    20000 DEF
103 krishna 45000 ABC
101 arjun   50000 ABC
106 karna 50000 ABC
102 bheem 65000 DEF
105 kiran  70000 DEF
```

**例 2:**

## c#

```cs
// C# program to sort a list of employees
// based on salary. Using OrderBy() method
using System;
using System.Linq;
using System.Collections.Generic;

class Geek{

int emp_id;
string Emp_Name;
int Emp_Salary;
string Emp_Department;

static void Main(string[] args)
{

    // Geeks data
    List<Geek> Geeks = new List<Geek>()
    {
        new Geek{emp_id = 201, Emp_Name = "Sumit", 
                 Emp_Salary = 50000, Emp_Department = "ABC"},
        new Geek{emp_id = 202, Emp_Name = "Rohan", 
                 Emp_Salary = 65000, Emp_Department = "DEF"},
        new Geek{emp_id = 203, Emp_Name = "Mohit", 
                 Emp_Salary = 45000, Emp_Department = "ABC"},
        new Geek{emp_id = 204, Emp_Name = "Sonam", 
                 Emp_Salary = 20000, Emp_Department = "DEF"},
        new Geek{emp_id = 205, Emp_Name = "Shive", 
                 Emp_Salary = 70000, Emp_Department = "DEF"},
    };

    // We have sorted the data using OrderBy linq clause
    var result_set = from emp in Geeks orderby emp.Emp_Salary select emp;

    // Display the sorted result
    foreach (Geek emp in result_set)
    {
        Console.WriteLine(emp.emp_id + " " + 
                          emp.Emp_Name + " " + 
                          emp.Emp_Salary + " " + 
                          emp.Emp_Department);
    }
}
}
```

**输出**

```cs
204 Sonam 20000 DEF
203 Mohit 45000 ABC
201 Sumit 50000 ABC
202 Rohan 65000 DEF
205 Shive 70000 DEF
```