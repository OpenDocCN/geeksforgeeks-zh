# LINQ |元素运算符| LastOrDefault

> 原文:[https://www . geesforgeks . org/linq-element-operator-lastordefault/](https://www.geeksforgeeks.org/linq-element-operator-lastordefault/)

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

#### LastOrDefault 运算符

最后一个运算符用于返回集合或序列的最后一个元素。或者返回指定给定条件的最后一个元素。或者如果给定集合不包含任何元素，则返回默认值。它克服了最后一种方法的*无效操作异常*问题。该方法可以通过两种不同的方式重载:

*   **LastOrDefault<t source>(IEnumerable<t source>):**此方法返回序列的最后一个元素，如果序列不包含元素，则返回默认值。
*   **LastOrDefault<t source>(IEnumerable<t source>，Func < TSource，Boolean > ):** 如果没有找到满足条件或默认值的序列的最后一个元素，则该方法返回该元素。

**要点:**

*   它不支持 C# 和 VB.Net 语言中的查询语法。
*   它支持 C# 和 VB.Net 语言中方法语法。
*   它同时出现在可查询类和可枚举类中。
*   引用类型和可空类型的默认值为 null。

**例 1:**

```cs
// C# program to illustrate the 
// use of LastOrDefault operator
using System;
using System.Linq;
using System.Collections.Generic;

class GFG {

    // Main Method
    static public void Main()
    {

        // Data source
        int[] sequence1 = {112, 44, 55, 66, 77, 777, 56};
        string[] sequence2 = {"Geeks", "GeeksforGeeks"};
        int[] sequence3 = {};

        // Get the element which specifies
        // the given condition Using the 
        // LastOrDefault(Condition) function
        var result1 = sequence1.LastOrDefault(seq => seq < 777);

        Console.WriteLine("Element: {0}", result1);

        // Get the only element of the sequence
        // Using LastOrDefault() function
        var result2 = sequence2.LastOrDefault();

        Console.WriteLine("Element: {0}", result2);

        // Get the default value
        var result3 = sequence3.LastOrDefault();

        Console.WriteLine("Default value: {0}", result3);
    }
}
```

**Output:**

```cs
Element: 56
Element: GeeksforGeeks
Default value: 0

```

**例 2:**

```cs
// C# program to find the 
// id of the last employee
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

            new Employee() {emp_id = 214, emp_name = "Anupriya", emp_gender = "Female",
                                         emp_hire_date = "17/6/2015", emp_salary = 50000},
        };

        // Query to find the id of the last 
        // employee Using LastOrDefault method
        var res = emp.Select(e => e.emp_id).LastOrDefault();

        Console.WriteLine("Employee Id: {0}", res);
    }
}
```

**Output:**

```cs
Employee Id: 214

```