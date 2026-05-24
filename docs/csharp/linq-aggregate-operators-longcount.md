# LINQ |聚合运算符|长计数

> 原文:[https://www . geesforgeks . org/linq-aggregate-operators-long count/](https://www.geeksforgeeks.org/linq-aggregate-operators-longcount/)

在 LINQ，计数操作符可用于计数给定序列或集合的元素。但是 count 运算符有一个缺点，就是它只对 MaxValue 起作用，也就是 *2147483647* ，如果你试图超过这个值，那么它会抛出一个*overowexception*。所以 LongCount 运算符克服了这个缺点。它允许您对大型集合或序列中存在的元素进行计数，只允许那些满足给定谓词函数的元素。或者换句话说，它返回一个表示序列或集合中元素数量的 *Int64* 值。该方法以两种不同的方式重载:

1.  **long count<t source>(IEnumerable<t source>，Func < TSource，Boolean > ):** 此方法用于返回一个 *Int64* 值，该值表示序列中有多少元素满足给定条件。
2.  **long count<t source>(IEnumerable<t source>):**此方法用于返回一个 Int64 值，该值代表给定序列或集合中存在的元素总数。

**要点:**

*   它不支持 C# 和 VB.Net 语言中的查询语法。
*   它可以支持 C# 和 VB.Net 语言的方法语法。
*   它同时出现在可查询类和可枚举类中。
*   如果源或谓词为空，它将引发 ArgumentNullException。
*   如果匹配元素的数量超过最大值，即 *9223372036854775807* ，它将抛出 OverflowException。

**例 1:**

```cs
// C# program to illustrate the
// use of LongCount method
using System;
using System.Linq;

class GFG {

    // Main Method
    static public void Main()
    {

        // Data source
        string[] sequence = {"Geeks", "gfg", "GeeksforGeeks", 
                               "GFG", "C#", "Java", "Python", 
                                   "WelcomeToGeeksforGeeks"};

        // Count how much elements present in
        // the sequence using LongCount function
        long res = sequence.LongCount(seq => seq.Length > 3);
        Console.WriteLine(res);
    }
}
```

**Output:**

```cs
5

```

**例 2:**

```cs
// C# program to find the total
// number of employees
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

        // Query to find the total
        // number of employees
        // using LongCount method
        long res = emp.Select(e => e.emp_id).LongCount();

        Console.WriteLine("How many employee present"+
                         " in the company: {0}", res);
    }
}
```

**Output:**

```cs
How many employee present in the company: 6

```