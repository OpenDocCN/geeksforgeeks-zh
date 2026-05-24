# LINQ |如何求给定序列的平均值？

> 原文:[https://www . geesforgeks . org/linq-如何找到给定序列的平均值/](https://www.geeksforgeeks.org/linq-how-to-find-average-of-the-given-sequence/)

在 LINQ，你可以使用**平均法**找到给定序列的平均值。此方法返回给定序列或集合中元素的平均值。它返回可空、不可空的十进制、双精度、浮点、int 等。价值观。它不支持 C# 中的查询语法，但在 VB.NET 支持。它在 C# 的可枚举和可查询类中都可用。

![](img/b7299584267baf12a166e7e658456732.png)

**例 1:**

```cs
// C# program to find the average 
// the given array
using System;
using System.Linq;

class GFG {

    static public void Main()
    {

        // Data source
        int[] sequence = { 20, 45, 50, 79, 90, 79, 89, 100, 567, 29 };

        // Display the sequence
        Console.WriteLine("The sequence is:");
        foreach(int s in sequence)
        {
            Console.WriteLine(s);
        }

        // Finding the average of the element 
        // present in the given array
        // Using Average function
        double result = sequence.Average();
        Console.WriteLine("Average is: {0}", result);
    }
}
```

**Output:**

```cs
The sequence is:
20
45
50
79
90
79
89
100
567
29
Average is: 114.8

```

**例 2:**

```cs
// C# program to find the average
// salary of the employee
using System;
using System.Linq;
using System.Collections.Generic;

// Employee details
class Employee {

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
            new Employee() { emp_id = 209, emp_name = "Anjita", emp_gender = "Female", emp_hire_date = "12/3/2017", emp_salary = 20000 },
                new Employee() { emp_id = 210, emp_name = "Soniya", emp_gender = "Female", emp_hire_date = "22/4/2018", emp_salary = 30000 },
                new Employee() { emp_id = 211, emp_name = "Rohit", emp_gender = "Male", emp_hire_date = "3/5/2016", emp_salary = 40000 },
                new Employee() { emp_id = 212, emp_name = "Supriya", emp_gender = "Female", emp_hire_date = "4/8/2017", emp_salary = 40000 },
                new Employee() { emp_id = 213, emp_name = "Anil", emp_gender = "Male", emp_hire_date = "12/1/2016", emp_salary = 40000 },
                new Employee() { emp_id = 214, emp_name = "Anju", emp_gender = "Female", emp_hire_date = "17/6/2015", emp_salary = 50000 },
        };

        // Find the average salary of the employee
        // Using Average () method
        var res = emp.Average(a => a.emp_salary);
        Console.WriteLine("Average salary of the Employees: {0}", res);
    }
}
```

**Output:**

```cs
Average salary of the Employees: 36666.6666666667

```