# LINQ |设置操作员|独特

> 原文:[https://www.geeksforgeeks.org/linq-set-operator-distinct/](https://www.geeksforgeeks.org/linq-set-operator-distinct/)

在 LINQ，集合运算符是查询表达式中返回结果集的运算符，该结果集基于相同或不同集合或序列或集合中等价元素的存在或不存在。标准查询运算符包含以下集合运算符:

1.  **工会**
2.  **相交**
3.  **除了**
4.  **不同**

#### 独特算子

Distinct 运算符返回不包含重复值的集合。或者换句话说，我们可以说这个运算符从集合或集合中移除所有重复的值，并返回一个包含唯一或不同值的集合或集合。

![](img/ca716f12689a9c1236625f45c94cd0ad.png)

*   它不支持 C# 和 VB.Net 语言中的查询语法。但是您可以对查询变量使用 Distinct 方法，或者您可以将查询包装在括号中，然后调用 Distinct 方法。
*   它支持 C# 和 VB.Net 语言中方法语法。
*   它同时出现在可查询类和可枚举类中。
*   它通过使用延迟执行来实现。
*   当您处理复杂类型的集合时，必须使用 IEqualityComparer 接口来使用 Distinct 方法，因为 Distinct 方法不比较复杂类型的值。

**例 1:**

```cs
// C# program to find the sequence 
// which contains unique elements
using System;
using System.Linq;

class GFG {

    static public void Main()
    {

        // Data source
        char[] sequence = {'m', 'q', 'o', 's', 'y', 
                          'a', 'a', 'c', 'y', 'o'};

        // Display the sequence
        Console.WriteLine("Sequence is: ");

        foreach(var s in sequence)
        {
            Console.WriteLine(s);
        }

        // Get the sequence which contains unique 
        // elements Using Distinct function
        var result = sequence.Distinct();

        Console.WriteLine("New Sequence: ");

        foreach(var val in result)
        {
            Console.WriteLine(val);
        }
    }
}
```

**Output:**

```cs
Sequence is: 
m
q
o
s
y
a
a
c
y
o
New Sequence: 
m
q
o
s
y
a
c

```

**例 2:**

```cs
// C# program to find the salary of 
// the employees with dissimilar values
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

        // Query to find the salary of the
        // employees with dissimilar values
        // Using Distinct method
        var res = emp.Select(e => e.emp_salary).Distinct();

        Console.WriteLine("Employee Salary: ");

        foreach(var val in res)
        {
            Console.WriteLine(val);
        }
    }
}
```

**Output:**

```cs
Employee Salary: 
20000
30000
40000
50000

```