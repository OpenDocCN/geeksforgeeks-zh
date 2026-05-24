# LINQ |分拣员|订单递减

> 原文:[https://www . geeksforgeeks . org/linq-sorting-operator-order by descending/](https://www.geeksforgeeks.org/linq-sorting-operator-orderbydescending/)

在 LINQ，排序运算符用于根据一个或多个属性以升序或降序重新排列给定的序列。LINQ 有 5 种不同类型的分拣操作员:

1.  [按](https://www.geeksforgeeks.org/linq-sorting-operator-orderby/)排序
2.  **按降序排序**
3.  **然后通过**
4.  **然后下降**
5.  **反转**

### 降序运算符

orderby 降序运算符用于按降序重新排列给定序列的元素。它不支持 C# 和 VB.Net 中的查询语法。它*只支持方法语法*。如果要在查询语法中以降序重新排列或排序给定序列或集合的元素，请使用降序关键字，如下例所示。
在方法语法中，使用 *OrderByDescending ()* 方法对给定序列或集合的元素进行排序。这个方法存在于可查询和可枚举类中。C# 和 VB.Net 语言都支持该方法语法。如下例所示。OrderByDescending 方法根据单个属性对集合的元素进行排序，不允许使用多个属性对集合进行排序。

**例 1:**

```cs
// C# program to print the employee
// ID in descending order
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

        // Query to print the ID of the
        // employees in descending order
        // Using Descending keyword in 
        // query syntax
        var res = from e in emp
                  orderby e.emp_id descending
                  select e;

        foreach(var val in res)
        {
            Console.WriteLine("Employee ID: {0}", val.emp_id);
        }
    }
}
```

**输出:**

```cs
Employee ID: 214
Employee ID: 213
Employee ID: 212
Employee ID: 211
Employee ID: 210
Employee ID: 209

```

**例 2:**

```cs
// C# program to print the employee
// name in descending order
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

        // Query to print the name of the
        // employees in descending order
        // Using OrderByDescending method
        var res = emp.OrderByDescending(e => e.emp_name);

        foreach(var val in res)
        {
            Console.WriteLine("Employee Name: {0}", val.emp_name);
        }
    }
}
```

**输出:**

```cs
Employee Name: Supriya
Employee Name: Soniya
Employee Name: Rohit
Employee Name: Anju
Employee Name: Anjita
Employee Name: Anil

```