# LINQ | Let 关键字

> 原文:[https://www.geeksforgeeks.org/linq-let-keyword/](https://www.geeksforgeeks.org/linq-let-keyword/)

有时，当我们使用查询表达式时，我们需要一个可以存储子表达式结果的变量，以便在即将到来的子句中重用它。这种类型的工具由 Let 关键字提供。Let 关键字允许您创建一个范围变量，并使用查询表达式的结果进行初始化，然后允许您在同一个查询中将该变量与即将到来的子句一起使用。当用一个值初始化一个范围变量时，不允许在范围变量中存储另一个值。

**例 1:**

```cs
// C# program to illustrate the
// concept of the let keyword
using System;
using System.Linq;

class GFG {

    // Main Method
    static public void Main()
    {

        // Data source
        int[] sequence = {2, 78, 90,
                          5, 45, 6};

        // Using let keyword
        var result = from s in sequence
            let a1
            = s + 100 where a1 > 150 select a1;

        // Display the result
        foreach(var val in result)
        {
            Console.WriteLine(val);
        }
    }
}
```

**Output:**

```cs
178
190

```

**说明:**在上例中，*结果*是存储给定查询表达式结果的查询变量。在查询表达式中，我们使用 *let* 关键字创建了一个范围变量，即 *a1* 。在 *a1* 中，我们存储 *s + 100* 表达式的结果。之后，我们在 where 子句中使用这个变量来比较每个元素是否大于 150，最后我们打印那些大于 *150* 的元素。

**例:2**

```cs
// C# program to print the name of those
// employees whose name contain more
// than 4 characters in lowercase
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

            new Employee() {emp_id = 209, emp_name = "ANU", emp_gender = "Female",
                                 emp_hire_date = "12/3/2017", emp_salary = 20000},

            new Employee() {emp_id = 210, emp_name = "SIYA", emp_gender = "Female",
                                  emp_hire_date = "22/4/2018", emp_salary = 30000},

            new Employee() {emp_id = 211, emp_name = "ROHIT", emp_gender = "Male",
                                  emp_hire_date = "3/5/2016", emp_salary = 40000},

            new Employee() {emp_id = 212, emp_name = "SUPRIYA", emp_gender = "Female",
                                      emp_hire_date = "4/8/2017", emp_salary = 40000},

            new Employee() {emp_id = 213, emp_name = "ANIL", emp_gender = "Male",
                                emp_hire_date = "12/1/2016", emp_salary = 40000},

            new Employee() {emp_id = 214, emp_name = "ANJU", emp_gender = "Female",
                                  emp_hire_date = "17/6/2015", emp_salary = 50000},
        };

        // Query to print the name of those
        // employees whose name contain more
        // than 4 characters in lowercase
        // Using let clause
        var res = from e in emp
            let name
            = e.emp_name.ToLower()
                where name.Length
            > 4 select name;

        foreach(var val in res)
        {
            Console.WriteLine("Employee Name: {0}", val);
        }
    }
}
```

**Output:**

```cs
Employee Name: rohit
Employee Name: supriya

```