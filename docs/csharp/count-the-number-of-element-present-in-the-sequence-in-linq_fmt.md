# 统计 LINQ 序列中存在的元素数量？

> 原文：[https://www.geeksforgeeks.org/count-the-number-of-element-present-in-the-sequence-in-linq/](https://www.geeksforgeeks.org/count-the-number-of-element-present-in-the-sequence-in-linq/)

在 LINQ 中，您可以使用 `Count` 方法来计数给定序列中存在的元素总数。此方法返回给定序列中存在的元素总数。

![](img/3dd02287ba7dfc2000ceb9fc24e157ae.png)

该方法可以通过两种不同的方式重载：

## 1. `Count<TSource>()`
此方法返回给定指定序列中存在的元素总数。此方法的返回类型是 `System.Int32`。如果源为 `null`，此方法会引发 `ArgumentNullException`；如果源的值很大，则会引发 `OverflowException`。它在 C# 中不支持查询语法，但您可以将查询用括号 `()` 包裹并使用聚合函数，如例 1 所示。它在 VB.NET 中支持查询语法。

**语法：**

```cs
int Count<TSource>();
```

## 2. `Count<TSource>(Func<TSource, bool> predicate)`
此方法用于返回满足给定条件的项数。此方法的返回类型是 `System.Int32`。如果源或谓词为 `null`，此方法会引发 `ArgumentNullException`；如果源的值很大，则会引发 `OverflowException`。

**语法：**

```cs
int Count<TSource>(Func<TSource, bool> predicate);
```

**注意：** VB.NET 不支持这种带谓词参数的方法。

## 例 1

```cs
// C# program to find total number of
// elements present in the given array
using System;
using System.Linq;

class GFG {

    // Main Method
    static public void Main()
    {
        // Data source
        int[] sequence = {6, 455, 50, 56, 102,
                          89, 9, 100, 67, 29};

        // Display the sequence
        Console.WriteLine("The sequence is: ");

        foreach(int s in sequence)
        {
            Console.WriteLine(s);
        }

        // Finding the total number of elements
        // present in the given sequence
        // Using Count function
        int result = sequence.Count();
        Console.WriteLine("Total number of Elements: {0}", result);
    }
}
```

**Output:**

```cs
The sequence is:
6
455
50
56
102
89
9
100
67
29
Total number of Elements: 10
```

## 例 2

```cs
// C# program to count the total
// number of the employees
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

        // Count the total number of employees
        // Using Count () method
        var res = (from e in emp
                   select e.emp_id)
                  .Count();

        Console.WriteLine("Total number of Employees: {0}", res);
    }
}
```

**Output:**

```cs
Total number of Employees: 6
```