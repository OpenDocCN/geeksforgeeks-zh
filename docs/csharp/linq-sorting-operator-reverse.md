# LINQ |分拣员|倒车

> 原文:[https://www . geesforgeks . org/linq-排序-运算符-反向/](https://www.geeksforgeeks.org/linq-sorting-operator-reverse/)

在 LINQ，排序运算符用于根据一个或多个属性以升序或降序重新排列给定的序列。LINQ 有 *5 种不同类型的分拣操作员*:

1.  [按](https://www.geeksforgeeks.org/linq-sorting-operator-orderby/)排序
2.  **按降序排序**
3.  **然后通过**
4.  **然后下降**
5.  **反转**

### 反向运算符

反转运算符用于反转序列或集合的顺序。与 [OrderBy 方法](https://www.geeksforgeeks.org/linq-sorting-operator-orderby/)不同，它在确定顺序时不考虑本身的实际值，而是以项目实际出现的相反顺序返回项目。
例如，当您在给定集合上使用*反转方法*时，集合以升序出现，它反转集合的顺序，即以降序出现。

*   它不支持 C# 和 VB.Net 语言中的查询语法。
*   它支持 C# 和 VB.Net 语言中方法语法。
*   它同时出现在可查询类和可枚举类中。
*   它通过使用延迟执行来实现。

**例 1:**

```cs
// C# program to reverse the order
// of the given array
using System;
using System.Linq;

class GFG {

    // Main Method
    static public void Main()
    {

        // Data source
        int[] sequence = {1, 2, 3, 4, 5, 6, 7};

        // Display the sequence
        Console.WriteLine("The Sequence is: ");

        foreach(int s in sequence)
        {
            Console.WriteLine(s);
        }

        // Reverse the given array
        // Using Reverse function
        var result = sequence.Reverse();

        Console.WriteLine("New Sequence:");
        foreach(var val in result)
        {
            Console.WriteLine(val);
        }
    }
}
```

**Output:**

```cs
The Sequence is: 
1
2
3
4
5
6
7
New Sequence:
7
6
5
4
3
2
1

```

**例 2:**

```cs
// C# program to print the 
// name of the employees
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
                                      emp_hire_date = "4/8/2017", emp_salary = 40000},

            new Employee() {emp_id = 213, emp_name = "Anil", emp_gender = "Male",
                                emp_hire_date = "12/1/2016", emp_salary = 40000},

            new Employee() {emp_id = 214, emp_name = "Anju", emp_gender = "Female",
                                  emp_hire_date = "17/6/2015", emp_salary = 50000},
        };

        // Query to print the name 
        // of the employees using
        // Reverse method
        var res = emp.OrderBy(e => e.emp_name).Reverse();

        foreach(var val in res)
        {
            Console.WriteLine("Employee Name: {0}", val.emp_name);
        }
    }
}
```

**Output:**

```cs
Employee Name: Supriya
Employee Name: Soniya
Employee Name: Rohit
Employee Name: Anju
Employee Name: Anjita
Employee Name: Anil

```