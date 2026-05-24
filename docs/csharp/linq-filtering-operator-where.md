# LINQ |过滤运算符|其中

> 原文:[https://www . geesforgeks . org/linq-filling-operator-where/](https://www.geeksforgeeks.org/linq-filtering-operator-where/)

过滤运算符是那些用于根据给定数据源或给定序列的用户要求过滤数据的运算符。例如，在员工记录中，我们希望获得年龄在 21 岁的员工的数据。所以，我们根据他们的年龄过滤记录。在 [LINQ](https://www.geeksforgeeks.org/linq-language-integrated-query/) 中，您可以使用以下运算符进行筛选:

1.  **where**
2.  The type of **is**

#### 哪里操作员

其中运算符根据谓词函数筛选值。或者换句话说，我们可以说它根据给定的条件或标准从序列中返回值。Where 子句不是查询中的强制子句。

**查询语法中的 Where 子句:**Where 子句用于根据给定的条件过滤查询。您可以使用 lambda 表达式或使用[函数委托](https://www.geeksforgeeks.org/c-sharp-func-delegate/)类型为 where 子句提供条件。Where 子句支持 [C# ](https://www.geeksforgeeks.org/csharp-programming-language/) 和 VB.Net 语言中的查询语法。Where 子句的查询语法如下例所示。

**例:**

```cs
// C# program to find the name of the 
// employees whose id less than equals
// to 211
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
                new Employee() { emp_id = 209, emp_name = "Anjita", emp_gender = "Female",
                                         emp_hire_date = "12/3/2017", emp_salary = 20000 },

                new Employee() { emp_id = 210, emp_name = "Soniya", emp_gender = "Female",
                                         emp_hire_date = "22/4/2018", emp_salary = 30000 },

                new Employee() { emp_id = 211, emp_name = "Rohit", emp_gender = "Male",
                                      emp_hire_date = "3/5/2016", emp_salary = 40000 },

                new Employee() { emp_id = 212, emp_name = "Supriya", emp_gender = "Female",
                                          emp_hire_date = "4/8/2017", emp_salary = 40000 },

                new Employee() { emp_id = 213, emp_name = "Anil", emp_gender = "Male", 
                                    emp_hire_date = "12/1/2016", emp_salary = 40000 },

                new Employee() { emp_id = 214, emp_name = "Anju", emp_gender = "Female",
                                      emp_hire_date = "17/6/2015", emp_salary = 50000 },
        };

        // Query to find the name of the 
        // employees whose id is less 
        // than equals to 211 Using where
        // clause in Query Syntax
        var res = from e in emp
                    where e.emp_id
                <= 211 select e.emp_name;

        foreach(var val in res)
        {
            Console.WriteLine("Employee Name: {0}", val);
        }
    }
}
```

**输出:**

```cs
Employee Name: Anjita
Employee Name: Soniya
Employee Name: Rohit

```