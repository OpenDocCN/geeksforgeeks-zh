# LINQ |分拣员|订单号

> 原文:[https://www . geesforgeks . org/linq-sorting-operator-order by/](https://www.geeksforgeeks.org/linq-sorting-operator-orderby/)

在 LINQ，排序运算符用于根据一个或多个属性以升序或降序重新排列给定的序列。LINQ 有 *5 种不同类型的分拣操作员*:

1.  排序依据
2.  **按降序排序**
3.  **然后通过**
4.  **然后下降**
5.  **反转**

#### 排序依据运算符

OrderBy 运算符用于按升序重新排列给定序列的元素。默认情况下，该运算符将给定序列的顺序转换为升序。不需要在查询表达式中添加额外的升序条件，这意味着升序关键字是可选的。您也可以使用降序关键字以降序更改给定序列的顺序。

**查询语法中的 order by:**order by 运算符支持 [C# ](https://www.geeksforgeeks.org/csharp-programming-language/) 和 VB.Net 语言中的查询语法。在查询语法中，orderby 词的用法如下例所示:

**示例:**

```cs
// C# program to print the employee
// name in ascending order
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

public class GFG {

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
                                     emp_hire_date = "4/8/2017", emp_salary = 40000 },

            new Employee() {emp_id = 213, emp_name = "Anil", emp_gender = "Male", 
                               emp_hire_date = "12/1/2016", emp_salary = 40000 },

            new Employee() {emp_id = 214, emp_name = "Anju", emp_gender = "Female",
                                 emp_hire_date = "17/6/2015", emp_salary = 50000 },
        };

        // Query to print the name of the
        // employee in ascending order
        // Using orderby clause in Query Syntax
        var res = from e in emp
                    orderby e.emp_name
                        select e.emp_name;

        foreach(var val in res)
        {
            Console.WriteLine("Employee Name: {0}", val);
        }
    }
}
```

**输出:**

```cs
Employee Name: Anil
Employee Name: Anjita
Employee Name: Anju
Employee Name: Rohit
Employee Name: Soniya
Employee Name: Supriya

```

**方法语法中的 OrderBy:**方法语法中的 order by 运算符以两种不同的类型重载:

*   **OrderBy < TSource，TKey>(IEnumerable<t source>，Func < TSource，TKey > ):** 该方法根据关键字对给定顺序的项目进行升序排序。
*   **OrderBy < TSource，TKey>(IEnumerable<t source>，Func < TSource，TKey >，IComparer < TKey > ):** 此方法使用指定的比较器按升序对给定序列的项目进行排序。

它同时出现在可查询类和可枚举类中。并支持 C# 和 VB.NET 语言中的方法语法。如下例所示:

**示例:**

```cs
// C# program to print the salary of
// the employees in ascending
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

public class GFG {

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
                                      emp_hire_date = "4/8/2017", emp_salary = 80000},

            new Employee() {emp_id = 213, emp_name = "Anil", emp_gender = "Male",
                                emp_hire_date = "12/1/2016", emp_salary = 60000},

            new Employee() {emp_id = 214, emp_name = "Anju", emp_gender = "Female",
                                  emp_hire_date = "17/6/2015", emp_salary = 50000},
        };

        // Print the salary of the employees
        // in ascending order using the 
        // OrderBy operator
        var res = emp.OrderBy(a => a.emp_salary);

        Console.WriteLine("Salary of the employees: ");

        foreach(var val in res)
        {
            Console.WriteLine(val.emp_salary);
        }
    }
}
```

**输出:**

```cs
Salary of the employees: 
20000
30000
40000
50000
60000
80000

```

#### 多重排序

在 LINQ，您可以在单个查询中对集合的多个字段进行排序，每个字段用逗号分隔。当您对集合执行多重排序时，首先根据第一个条件进行排序，然后如果给定集合中的两个字段相似，则排序第二个字段，依此类推。如下例所示，emp_salary 包含两个相似的值，因此排序是根据 emp_id 进行的。

**示例:**

```cs
// C# program to illustrate multiple sorting
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

public class GFG {

    // Main method
    static public void Main()
    {
        List<Employee> emp = new List<Employee>() {

            new Employee() {emp_id = 209, emp_name = "Anjita", emp_gender = "Female",
                                    emp_hire_date = "12/3/2017", emp_salary = 20000},

            new Employee() {emp_id = 210, emp_name = "Soniya", emp_gender = "Female",
                                    emp_hire_date = "22/4/2018", emp_salary = 20000},

            new Employee() {emp_id = 211, emp_name = "Rohit", emp_gender = "Male",
                                  emp_hire_date = "3/5/2016", emp_salary = 40000},

            new Employee() {emp_id = 212, emp_name = "Supriya", emp_gender = "Female",
                                      emp_hire_date = "4/8/2017", emp_salary = 80000},

            new Employee() {emp_id = 213, emp_name = "Anil", emp_gender = "Male",
                                emp_hire_date = "12/1/2016", emp_salary = 60000},

            new Employee() {emp_id = 214, emp_name = "Anju", emp_gender = "Female",
                                  emp_hire_date = "17/6/2015", emp_salary = 50000},
        };

        // Perform multiple sorting
        var res = from e in emp
                    orderby e.emp_salary, e.emp_id
                      select e;

        foreach(var val in res)
        {
            Console.WriteLine("Employee Salary: {0} Employee Id: {1}",
                                          val.emp_salary, val.emp_id);
        }
    }
}
```

**输出:**

```cs
Employee Salary: 20000 Employee Id: 209
Employee Salary: 20000 Employee Id: 210
Employee Salary: 40000 Employee Id: 211
Employee Salary: 50000 Employee Id: 214
Employee Salary: 60000 Employee Id: 213
Employee Salary: 80000 Employee Id: 212

```