# LINQ |元素操作员|元素 At

> 原文:[https://www . geesforgeks . org/linq-element-operator-element at/](https://www.geeksforgeeks.org/linq-element-operator-elementat/)

元素运算符用于从序列或集合中返回单个元素或特定元素。比如在一所学校当我们问，谁是校长？那么只有一个人会成为学校的校长。所以学生的数量是一个集合，校长是这个集合的唯一结果。

LINQ 标准查询运算符支持 **8 种类型的**元素运算符:

1.  **元素**
2.  **元素默认值**
3.  **第一**
4.  **一阶违约**
5.  **最后**
6.  **货物订货标准**
7.  **单**
8.  **单字错误**

#### elemontat 算子

ElementAt 运算符用于从给定集合或序列的特定索引中返回元素。这里指定的索引是从零开始的索引。假设一个数组包含 3 个元素，即 1、2、3，我们想打印索引 1 处的值，所以我们使用 ElementAt 方法，因为它将返回索引 1 处存在的元素，即 2。

**要点:**

*   它不支持 C# 和 VB.Net 语言中的查询语法。
*   它支持 C# 和 VB.Net 语言中方法语法。
*   它同时出现在可查询类和可枚举类中。
*   如果给定的索引超出范围，那么这个方法将抛出一个*argumentout of range exception*。

**例 1:**

```cs
// C# program to illustrate the
// use of ElementAt operator
using System;
using System.Linq;

class GFG {

    // Main Method
    static public void Main()
    {

        // Data source
        string[] sequence = {"Dog", "Cat", "Cow",
                               "Goat", "Parrot"};

        // Display the sequences
        Console.WriteLine("Sequence is: ");

        foreach(var s in sequence)
        {
            Console.WriteLine(s);
        }

        // Get element at index 3
        // Using ElementAt function
        var result = sequence.ElementAt(3);

        Console.WriteLine("Element is: {0}", result);
    }
}
```

**Output:**

```cs
Sequence is: 
Dog
Cat
Cow
Goat
Parrot
Element is: Goat

```

**例 2:**

```cs
// C# program to find the 
// ID of the employee
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

        // Query to find the ID of 
        // the employee at index 1
        // Using ElementAt method
        var res = emp.Select(e => e.emp_id).ElementAt(1);

        Console.WriteLine("Employee ID: {0}", res);
    }
}
```

**Output:**

```cs
Employee ID: 210

```