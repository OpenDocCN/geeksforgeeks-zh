# LINQ |元素操作员|元素默认

> 原文:[https://www . geeksforgeeks . org/linq-element-operator-element ator default/](https://www.geeksforgeeks.org/linq-element-operator-elementatordefault/)

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

#### elemontatordefault 运算符

*ElementAtOrDefault* 运算符用于从给定集合或序列的特定索引中返回一个元素，如果索引超出范围，它将提供一个默认值。它克服了*元素在*操作符上的*argumentout of range exception*问题。

*   它不支持 C# 和 VB.Net 语言中的查询语法。
*   它支持 C# 和 VB.Net 语言中方法语法。
*   它同时出现在可查询类和可枚举类中。
*   当索引超出范围时，它不会引发 ArgumentOutOfRangeException。
*   引用类型和可空类型的默认值为 null。

**例 1:**

```cs
// C# program to illustrate the use 
// of ElementAtOrDefault operator
using System;
using System.Linq;

class GFG {

    static public void Main()
    {

        // Data source
        string[] sequence1 = {"Dog", "Cat", "Goat", "Parrot"};
        int[] sequence2 = {112, 44, 55, 66, 77, 777, 56};

        // Get the element at the given index
        // Using ElementAtOrDefault function
        var result1 = sequence1.ElementAtOrDefault(2);
        Console.WriteLine("Element at index 2 in sequence 1: {0}", result1);

        var result2 = sequence1.ElementAtOrDefault(4);
        Console.WriteLine("Element at index 4 in sequence 1: {0}", result2);

        var result3 = sequence1.ElementAtOrDefault(6);
        Console.WriteLine("Element at index 6 in sequence 1: {0}", result3);

        var result4 = sequence2.ElementAtOrDefault(2);
        Console.WriteLine("Element at index 2 in sequence 2: {0}", result4);

        var result5 = sequence2.ElementAtOrDefault(5);
        Console.WriteLine("Element at index 5 in sequence 2: {0}", result5);

        var result6 = sequence2.ElementAtOrDefault(8);
        Console.WriteLine("Element at index 8 in sequence 2: {0}", result6);
    }
}
```

**Output:**

```cs
Element at index 2 in sequence 1: Goat
Element at index 4 in sequence 1: 
Element at index 6 in sequence 1: 
Element at index 2 in sequence 2: 55
Element at index 5 in sequence 2: 777
Element at index 8 in sequence 2: 0

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
        // the employee at index 3
        // Using ElementAtOrDefault method
        var res = emp.Select(e => e.emp_id).ElementAtOrDefault(3);

        Console.WriteLine("Employee ID: {0}", res);
    }
}
```

**Output:**

```cs
Employee ID: 212

```