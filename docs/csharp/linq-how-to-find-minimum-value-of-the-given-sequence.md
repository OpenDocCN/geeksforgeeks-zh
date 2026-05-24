# LINQ |如何求给定序列的最小值？

> 原文:[https://www . geesforgeks . org/linq-如何找到给定序列的最小值/](https://www.geeksforgeeks.org/linq-how-to-find-minimum-value-of-the-given-sequence/)

在 LINQ，你可以使用 **Min()函数**找到给定序列的最小元素。此方法提供给定值集中的最小元素。它不支持 C# 中的查询语法，但在 VB.NET 支持。它在 C# 的可枚举和可查询类中都可用。如果集合中存在的所有元素都为 null，则返回 null。它返回任何类型的数据类型，这意味着您也可以将 Min 用于自定义类型的集合(不包含数值)，但为此，您必须实现 IComparable 接口。它可以处理可空、不可空的十进制、双精度、浮点、int 等。价值观。

![](img/329c9c48cea6eee8e34f3e9c82bc9f50.png)

**例 1:**

```cs
// C# program to find minimum
// value from the given array
using System;
using System.Linq;

class GFG {

    // Main Method
    static public void Main()
    {

        // Data source
        int[] sequence = {20, 45, 50, 79, 90,
                       79, 89, 100, 567, 29};

        // Display the sequence
        Console.WriteLine("The sequence is: ");

        foreach(int s in sequence)
        {
            Console.WriteLine(s);
        }

        // Finding the minimum element
        // from the given sequence
        // Using Min function
        int result = sequence.Min();
        Console.WriteLine("Minimum Value: {0}", result);
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
Minimum Value: 20

```

**例 2:**

```cs
// C# program to find the Minimum
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

        // Find the minimum salary 
        // of the employee
        // Using Min () method
        var res = emp.Min(a => a.emp_salary);
        Console.WriteLine("Minimum salary of the employee: {0}", res);
    }
}
```

**Output:**

```cs
Minimum salary of the employee: 20000

```