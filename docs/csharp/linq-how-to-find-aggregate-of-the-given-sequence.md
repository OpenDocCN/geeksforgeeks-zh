# LINQ |如何找到给定序列的聚合？

> 原文:[https://www . geesforgeks . org/linq-如何找到给定序列的聚合/](https://www.geeksforgeeks.org/linq-how-to-find-aggregate-of-the-given-sequence/)

在 LINQ，您可以使用聚合方法创建自己的自定义聚合操作。此方法允许您对集合或序列的值执行自定义聚合操作。它不支持 C# 和 VB.Net 语言的查询语法，但可以支持两种语言的[方法语法](https://www.geeksforgeeks.org/linq-method-syntax/)。它同时出现在可查询类和可枚举类中。这种方法在 **3** 中以不同的方式超载:

1.  **聚合<t 源，t 累计，t 结果>(IEnumerable<t 源>，t 累计，Func<t 累计，t 源，t 累计>，Func<t 累计，t 结果> ):** 此方法用于对序列应用累加器函数。指定的种子值用作初始累加器值，指定的函数用于选择结果值。
2.  **聚合<源，累计> (IEnumerable <源>，累计，函数<累计，源，累计> ):** 此方法对序列应用一个累加器函数。指定的种子值用作初始累加器值。
3.  **聚合<源> (IEnumerable <源>，函数<源，源，源> ):** 此方法对序列应用累加器函数。

**例 1:**

```cs
// C# program to illustrate the
// use of aggregate method
using System;
using System.Linq;

class GFG {

    // Main Method
    static public void Main()
    {

        // Data source
        string[] sequence = {"Geeks", "gfg", 
                    "GeeksforGeeks", "GFG"};

        // Concatenate the element of the 
        // given sequence using Aggregate function
        var result = sequence.Aggregate((q1, q2) => q1 + "-" + q2);
        Console.WriteLine(result);
    }
}
```

**Output:**

```cs
Geeks-gfg-GeeksforGeeks-GFG

```

**解释:*中的***var 结果=序列。合计((q1，Q2)=>Q1+"-"+Q2)；，首先它获取 Geeks 和 *gfg* 元素，并在它们之间执行串联操作，然后它获取这个结果来与 GeeksfoGeeks 元素进行串联。同样，这个结果被用来执行与 GFG 元素的连接操作，最后最终结果被存储在结果变量中。或者简单的说就是:*((极客-gfg)-极客-GFG)*

**例 2:**

```cs
// C# program to find the total 
// salary of the employees
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

        // Query to find the total salary
        // of the employees
        // Using Aggregate method
        var res = emp.Select(e => e.emp_salary).Aggregate((x,
                                                y) => x + y);

        Console.WriteLine("Total salary of the Employees: {0}", res);
    }
}
```

**Output:**

```cs
Total salary of the Employees: 220000

```

**解释:**聚合方法在这个 var res = emp 中的工作。选择(e =>e . EMP _ 薪资)。聚合((x，y)=>x+y)；声明是:

> (20000, 30000) => 20000 + 30000;
> (50000，40000)=>50000+40000；
> (50000，40000)=>130000+40000；
> (13 万，4 万)= > 17 万+ 4 万；
> (17 万，5 万)= > 17 万+ 5 万；
> RES 的最终储值为 220000

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . linq . enumerable . aggregate？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.linq.enumerable.aggregate?view=netframework-4.8)