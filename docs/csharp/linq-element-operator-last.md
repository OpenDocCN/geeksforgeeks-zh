# LINQ |元素运算符|最后一个

> 原文:[https://www.geeksforgeeks.org/linq-element-operator-last/](https://www.geeksforgeeks.org/linq-element-operator-last/)

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

#### 最后一个操作员

最后一个运算符用于返回集合或序列的最后一个元素。或者返回指定给定条件的最后一个元素。该方法可以通过两种不同的方式重载:

*   **Last<t source>(IEnumerable<t source>):**此方法返回给定集合或序列的最后一个元素。
*   **Last<t source>(IEnumerable<t source>，Func < TSource，Boolean > ):** 该方法根据给定条件返回最后一个元素。

**要点:**

*   它不支持 C# 和 VB.Net 语言中的查询语法。
*   它支持 C# 和 VB.Net 语言中方法语法。
*   它同时出现在可查询类和可枚举类中。
*   如果序列不包含指定给定条件的元素，或者序列为空，则抛出*无效操作异常*。

**例 1:**

```cs
// C# program to illustrate the 
// use of Last operator
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

        // Get the element which specifies
        // the given condition Using 
        // Last(Condition) function
        var result1 = sequence1.Last(seq => seq < 777);

        Console.WriteLine("Element: {0}", result1);

        // Get the only element of the 
        // sequence Using Last() function
        var result2 = sequence2.Last();

        Console.WriteLine("Element: {0}", result2);

        // This commented part will give 
        // InvalidOperationException because
        // the sequence does not contain element
        /*
            int[] sequence3 = {};
            var result3 = sequence3.Last();
            Console.WriteLine("Element: {0}", result3);
        */
    }
}
```

**Output:**

```cs
Element: 56
Element: GeeksforGeeks

```

**例 2:**

```cs
// C# program to find the last 
// name of the employee
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

        // Query to find the name
        // of the last employee
        // Using Last method
        var res = emp.Select(e => e.emp_name).Last();

        Console.WriteLine("Employee name: {0}", res);
    }
}
```

**Output:**

```cs
Employee name: Anupriya

```