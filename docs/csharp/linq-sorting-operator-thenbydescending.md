# LINQ |分拣员|然后下降

> 原文:[https://www . geeksforgeeks . org/linq-sorting-operator-then by descending/](https://www.geeksforgeeks.org/linq-sorting-operator-thenbydescending/)

在 LINQ，排序运算符用于根据一个或多个属性以升序或降序重新排列给定的序列。LINQ 有 5 种不同类型的分拣操作员:

1.  [按](https://www.geeksforgeeks.org/linq-sorting-operator-orderby/)排序
2.  **[降序](https://www.geeksforgeeks.org/linq-sorting-operator-orderbydescending/)**
3.  **[然后通过](https://www.geeksforgeeks.org/linq-sorting-operator-thenby/)**
4.  **然后下降**
5.  **[倒车](https://www.geeksforgeeks.org/linq-sorting-operator-reverse/)**

#### 然后是递减运算符

ThenByDescending 运算符用于以降序实现二级排序。通过*然后通过*下降操作符支持多重排序。一般来说，降阶法与*降阶法一起使用。 *OrderBy()* 方法先对序列或集合的元素进行降序排序，然后*再用*方法对 *OrderBy()* 方法的结果再次进行降序排序。或者换句话说，在 LINQ，集合是根据 OrderBy 方法给出的主字段进行的第一次排序，然后主排序的结果再次由*然后是*方法给出的次字段进行排序。*

*   它不支持 C# 和 VB.Net 语言中的查询语法。
*   它支持 C# 和 VB.Net 语言中方法语法。
*   它同时出现在可查询类和可枚举类中。
*   查询语法中的二级排序用逗号分隔。
*   它通过使用延迟执行来实现。

**例 1:**

```cs
// C# program to print the employees
// name and their salary
using System;
using System.Linq;
using System.Collections.Generic;

// Employee details
public class Employee {

    public int emp_id
    {
        get;
        set;
    }

    public string emp_name
    {
        get;
        set;
    }

    public string emp_gender
    {
        get;
        set;
    }

    public string emp_hire_date
    {
        get;
        set;
    }

    public int emp_salary
    {
        get;
        set;
    }
}

class GFG {

    // Main method
    static public void Main()
    {
        List<Employee> emp = new List<Employee>() {

            new Employee() {emp_id = 209, emp_name = "Anjita", emp_gender = "Female",
                                    emp_hire_date = "12/3/2017", emp_salary = 20000},

            new Employee() {emp_id = 210, emp_name = "Soniya", emp_gender = "Female",
                                    emp_hire_date = "22/4/2018", emp_salary = 30000},

            new Employee() {emp_id = 211, emp_name = "Rohit", emp_gender = "Male",
                                  emp_hire_date = "3/5/2016", emp_salary = 40000},

            new Employee() {emp_id = 212, emp_name = "Supriya", emp_gender = "Female",
                                      emp_hire_date = "4/8/2017", emp_salary = 40000},

            new Employee() {emp_id = 213, emp_name = "Anil", emp_gender = "Male",
                                emp_hire_date = "12/1/2016", emp_salary = 40000},

            new Employee() {emp_id = 214, emp_name = "Anju", emp_gender = "Female",
                                  emp_hire_date = "17/6/2015", emp_salary = 50000},
        };

        // Query to print the name and
        // salary of the employees
        // Using OrderByDescending and
        // ThenByDescending method
        var res = emp.OrderByDescending(e => 
           e.emp_name).ThenByDescending(e =>
                              e.emp_salary);

        foreach(var val in res)
        {
            Console.WriteLine("Employee Name: {0}  Salary: {1}",
                                    val.emp_name, val.emp_salary);
        }
    }
}
```

**Output:**

```cs
Employee Name: Supriya  Salary: 40000
Employee Name: Soniya  Salary: 30000
Employee Name: Rohit  Salary: 40000
Employee Name: Anju  Salary: 50000
Employee Name: Anjita  Salary: 20000
Employee Name: Anil  Salary: 40000

```

**例 2:**

```cs
// C# program to print the employees
// IDs and their salary
using System;
using System.Linq;
using System.Collections.Generic;

// Employee details
public class Employee {

    public int emp_id
    {
        get;
        set;
    }

    public string emp_name
    {
        get;
        set;
    }

    public string emp_gender
    {
        get;
        set;
    }

    public string emp_hire_date
    {
        get;
        set;
    }

    public int emp_salary
    {
        get;
        set;
    }
}

class GFG {

    // Main method
    static public void Main()
    {
        List<Employee> emp = new List<Employee>() {

            new Employee() {emp_id = 209, emp_name = "Anjita", emp_gender = "Female",
                                    emp_hire_date = "12/3/2017", emp_salary = 20000},

            new Employee() {emp_id = 210, emp_name = "Soniya", emp_gender = "Female",
                                    emp_hire_date = "22/4/2018", emp_salary = 30000},

            new Employee() {emp_id = 211, emp_name = "Rohit", emp_gender = "Male",
                                  emp_hire_date = "3/5/2016", emp_salary = 40000},

            new Employee() {emp_id = 212, emp_name = "Supriya", emp_gender = "Female",
                                      emp_hire_date = "4/8/2017", emp_salary = 40000},

            new Employee() {emp_id = 213, emp_name = "Anil", emp_gender = "Male",
                                emp_hire_date = "12/1/2016", emp_salary = 40000},

            new Employee() {emp_id = 214, emp_name = "Anju", emp_gender = "Female",
                                  emp_hire_date = "17/6/2015", emp_salary = 50000},
        };

        // Query to print the IDs and
        // salary of the employees
        // Using OrderBy and ThenByDescending 
        // method
        var res = emp.OrderBy(e => 
            e.emp_id).ThenByDescending(e => 
                              e.emp_salary);

        foreach(var val in res)
        {
            Console.WriteLine("Employee ID: {0} Salary: {1}"
                              , val.emp_id, val.emp_salary);
        }
    }
}
```

**Output:**

```cs
Employee ID: 209 Salary: 20000
Employee ID: 210 Salary: 30000
Employee ID: 211 Salary: 40000
Employee ID: 212 Salary: 40000
Employee ID: 213 Salary: 40000
Employee ID: 214 Salary: 50000

```