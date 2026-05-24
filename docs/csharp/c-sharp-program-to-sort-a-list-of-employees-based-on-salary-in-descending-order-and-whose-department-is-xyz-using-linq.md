# C# 程序，使用 LINQ

根据工资降序排列员工列表，以及谁的部门是 XYZ

> 原文:[https://www . geeksforgeeks . org/c-sharp-program-to-sort-a-list-employees-based-in-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-sort-a-list-of-employees-based-on-salary-in-descending-order-and-whose-department-is-xyz-using-linq/)

给定一份员工名单，现在我们按照工资降序排列，谁的部门是 XYZ。所以我们使用 LINQ 的 [OrderByDescending()](https://www.geeksforgeeks.org/linq-sorting-operator-orderbydescending/) 方法和 [Where()](https://www.geeksforgeeks.org/linq-filtering-operator-where/) 方法。OrderByDescending()用于按降序对指定列表进行排序。为了解决给定的问题，我们使用以下 LINQ 查询:

> var result_set = Geeks。其中(emp= > emp。EMP _ Department = =“XYZ”)。OrderByDescending(sal = > sal。Emp _ 薪资)；

这里，Where()方法查找部门为“XYZ”的员工，OrderByDescending()方法根据他们的工资按降序对他们进行排序。

**例:**

```cs
Input: {id = 202, Name = Mohit, Salary = 10000, Depertment = XYZ}
       {id = 204, Name = Sumit, Salary = 20000, Depertment = ABC}
       {id = 205, Name = Pritam, Salary = 80000, Depertment = ABC}
       {id = 206, Name = Poonam, Salary = 30000, Depertment = XYZ}
Output: {id = 206, Name = Poonam, Salary = 30000, Depertment = XYZ}
        {id = 202, Name = Mohit, Salary = 10000, Depertment = XYZ}
```

## c#

```cs
// C# program to sort a list of employees based on 
// salary in descending order and whose department is XYZ
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

    // List to store the details of employees
    List<Geek> Geeks = new List<Geek>()
    {
        new Geek{emp_id = 101, Emp_Name = "Amit", 
                 Emp_Salary = 50000,Emp_Department = "XYZ"},
        new Geek{emp_id = 102, Emp_Name = "Poonam", 
                 Emp_Salary = 65000,Emp_Department = "ABC"},
        new Geek{emp_id = 103, Emp_Name = "Priya", 
                 Emp_Salary = 45000,Emp_Department = "ABC"},
        new Geek{emp_id = 104, Emp_Name = "Sita", 
                 Emp_Salary = 20000,Emp_Department = "XYZ"},
        new Geek{emp_id = 105, Emp_Name = "kiran", 
                 Emp_Salary = 70000,Emp_Department = "ABC"},
        new Geek{emp_id = 106, Emp_Name = "Sohan", 
                 Emp_Salary = 40000,Emp_Department = "XYZ"},
    };

    // Using the where command we have selected the
    // geeks having XYZ department and then we have 
    // sorted the data in descending order using 
    // OrderByDescending() command
    var result_set = Geeks.Where(emp => emp.Emp_Department == "XYZ").OrderByDescending(
                                 sal => sal.Emp_Salary);

    // Display the results
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

**输出:**

```cs
101 Amit 50000 XYZ
106 Sohan 40000 XYZ
104 Sita 20000 XYZ
```