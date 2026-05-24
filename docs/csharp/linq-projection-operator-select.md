# LINQ |投影操作员|选择

> 原文:[https://www . geesforgeks . org/linq-projection-operator-select/](https://www.geeksforgeeks.org/linq-projection-operator-select/)

在 LINQ，投影是一种将一个对象转换成新形式的操作，新形式只保留那些随后将被使用的属性。通过使用投影，开发人员可以创建一个由每个对象构建的新类型。你可以投射属性并对其进行数学函数运算，也可以投射原始对象而不进行变换。

在 LINQ，可以进行以下投影操作:

1.  **选择**
2.  **选取多个**

#### 选择操作员

select 运算符返回 IEnumerator 集合，该集合保存基于转换函数的项。或者换句话说，我们可以说，当您想要从给定集合中选择单个值时，使用 select 运算符。

**使用查询语法选择:**在 LINQ，使用查询语法创建查询时使用选择运算符。在查询表达式中，表达式以 Select 或 GroupBy 子句结束。在查询中，select 运算符用于返回自定义类或匿名类型的集合，该集合包含用户需要的属性，还用于根据用户需要操作结果。选择运算符支持 C# 和`VB.NET`语言的查询语法，如下例所示:

**示例:**

```cs
// C# program to find the name 
// of the employee
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
            new Employee() { emp_id = 209, emp_name = "Anjita", emp_gender = "Female", emp_hire_date = "12/3/2017", emp_salary = 20000 },
                new Employee() { emp_id = 210, emp_name = "Soniya", emp_gender = "Female", emp_hire_date = "22/4/2018", emp_salary = 30000 },
                new Employee() { emp_id = 211, emp_name = "Rohit", emp_gender = "Male", emp_hire_date = "3/5/2016", emp_salary = 40000 },
                new Employee() { emp_id = 212, emp_name = "Supriya", emp_gender = "Female", emp_hire_date = "4/8/2017", emp_salary = 40000 },
                new Employee() { emp_id = 213, emp_name = "Anil", emp_gender = "Male", emp_hire_date = "12/1/2016", emp_salary = 40000 },
                new Employee() { emp_id = 214, emp_name = "Anju", emp_gender = "Female", emp_hire_date = "17/6/2015", emp_salary = 50000 },
        };

        // Query to find the name of the employee
        // Using select in  Query Syntax
        var res = from e in emp
                      select e.emp_name;

        foreach(var val in res)
        {
            Console.WriteLine("Employee Name: {0}", val);
        }
    }
}
```

**Output:**

```cs
Employee Name: Anjita
Employee Name: Soniya
Employee Name: Rohit
Employee Name: Supriya
Employee Name: Anil
Employee Name: Anju

```

**使用方法语法进行选择:**在方法语法中，Select 运算符是可选的，您可以使用它来塑造数据。可查询类和可枚举类中都有 Select 方法。它支持 C# 和 VB.Net 语言中的方法语法。下面的示例显示了 select 方法的用法。

**示例:**

```cs
// C# program to find the name 
// and id of the employee
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
            new Employee() { emp_id = 209, emp_name = "Anjita", emp_gender = "Female", emp_hire_date = "12/3/2017", emp_salary = 20000 },
                new Employee() { emp_id = 210, emp_name = "Soniya", emp_gender = "Female", emp_hire_date = "22/4/2018", emp_salary = 30000 },
                new Employee() { emp_id = 211, emp_name = "Rohit", emp_gender = "Male", emp_hire_date = "3/5/2016", emp_salary = 40000 },
                new Employee() { emp_id = 212, emp_name = "Supriya", emp_gender = "Female", emp_hire_date = "4/8/2017", emp_salary = 40000 },
                new Employee() { emp_id = 213, emp_name = "Anil", emp_gender = "Male", emp_hire_date = "12/1/2016", emp_salary = 40000 },
                new Employee() { emp_id = 214, emp_name = "Anju", emp_gender = "Female", emp_hire_date = "17/6/2015", emp_salary = 50000 },
        };

        // finding the name and id of the 
        // employee Using select method
        var res = emp.Select(a => new { ID = a.emp_id, Name = a.emp_name });

        foreach(var val in res)
        {
            Console.WriteLine("Employee Name : {0}  Employee ID : {1}",
                                                     val.Name, val.ID);
        }
    }
}
```

**Output:**

```cs
Employee Name : Anjita  Employee ID : 209
Employee Name : Soniya  Employee ID : 210
Employee Name : Rohit  Employee ID : 211
Employee Name : Supriya  Employee ID : 212
Employee Name : Anil  Employee ID : 213
Employee Name : Anju  Employee ID : 214

```