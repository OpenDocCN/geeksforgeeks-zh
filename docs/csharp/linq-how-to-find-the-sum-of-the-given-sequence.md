# LINQ |如何求给定序列的和？

> 原文:[https://www . geesforgeks . org/linq-如何找到给定序列的和/](https://www.geeksforgeeks.org/linq-how-to-find-the-sum-of-the-given-sequence/)

在 LINQ，你可以使用 **Sum()方法**找到给定数值元素的和。此方法计算给定序列中存在的数值之和。它不支持 C# 中的查询语法，但是在*VB.NET*中支持。它在 C# 的可枚举和可查询类中都可用。它可以处理可空、不可空的十进制、双精度、浮点、int 等。价值观。

![](img/ad17162b1b141c1d5d25d125e74c4de5.png)

**例 1:**

```cs
// C# program to illustrate how to
// find the sum of the given sequence
using System;
using System.Linq;

class GFG {

    // Main Method
    static public void Main()
    {

        int[] sequence = { 20, 30, 50, 78, 90,
                           79, 89, 99, 97, 29 };

        // Display the sequence
        Console.WriteLine("The Sequence is: ");

        foreach(int s in sequence)
        {
            Console.WriteLine(s);
        }

        // Finding sum of the given sequence
        // Using Sum function
        int result = sequence.Sum();
        Console.WriteLine("The sum of the given "
                              + "sequence is: {0}",
                          result);
    }
}
```

**Output:**

```cs
The Sequence is: 
20
30
50
78
90
79
89
99
97
29
The sum of the given sequence is: 661

```

**例 2:**

```cs
// C# program to find the sum
// of the salary of the employee
using System;
using System.Linq;
using System.Collections.Generic;

// Employee details
public class employee {
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
        List<employee> emp = new List<employee>() {
            new employee() { emp_id = 209, emp_name = "Anjita", emp_gender = "Female", emp_hire_date = "12/3/2017", emp_salary = 20000 },
                new employee() { emp_id = 210, emp_name = "Soniya", emp_gender = "Female", emp_hire_date = "22/4/2018", emp_salary = 30000 },
                new employee() { emp_id = 211, emp_name = "Rohit", emp_gender = "Male", emp_hire_date = "3/5/2016", emp_salary = 40000 },
                new employee() { emp_id = 212, emp_name = "Supriya", emp_gender = "Female", emp_hire_date = "4/8/2017", emp_salary = 40000 },
                new employee() { emp_id = 213, emp_name = "Anil", emp_gender = "Male", emp_hire_date = "12/1/2016", emp_salary = 40000 },
                new employee() { emp_id = 214, emp_name = "Anju", emp_gender = "Female", emp_hire_date = "17/6/2015", emp_salary = 50000 },
        };

        // Find the sum of the salary
        // Using Sum () method
        var res = emp.Sum(a = > a.emp_salary);
        Console.WriteLine("Total salary of the Employees: {0}", res);
    }
}
```

**Output:**

```cs
Total salary of the Employees: 220000

```