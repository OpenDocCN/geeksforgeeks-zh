# LINQ |元素操作员|单个

> 原文:[https://www.geeksforgeeks.org/linq-element-operator-single/](https://www.geeksforgeeks.org/linq-element-operator-single/)

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

#### 单一操作员

单个运算符用于返回集合或序列的单个元素。或者它返回指定给定条件的单个元素。该方法可以通过两种不同的方式重载:

*   **Single<t source>(IEnumerable<t source>，Func < TSource，Boolean > ):** 此方法返回集合或序列中指定给定条件的唯一元素，如果存在多个指定给定条件的元素，将引发异常。
*   **Single<t source>(IEnumerable<t source>):**此方法返回给定序列或集合中的唯一元素，如果序列或集合中没有恰好一个元素，则抛出异常。

**要点:**

*   它不支持 C# 和 VB.Net 语言中的查询语法。
*   它支持 C# 和 VB.Net 语言中方法语法。
*   它同时出现在可查询类和可枚举类中。
*   如果序列不包含指定给定条件的元素，或者包含多个指定给定条件的元素，或者序列为空，则抛出*invalidOperationException*。

**例 1:**

```cs
// C# program to illustrate the
// use of Single operator
using System;
using System.Linq;
using System.Collections.Generic;

class GFG {

    static public void Main()
    {

        // Data source
        int[] sequence1 = {112, 44, 55, 66, 77, 777, 56};
        int[] sequence2 = {2};

        // Get the element which specifies the given 
        // condition Using Single(Condition) function
        var result1 = sequence1.Single(seq => seq == 112);

        Console.WriteLine("Element: {0}", result1);

        // Get the only element of the 
        // sequence Using Single() function
        var result2 = sequence2.Single();

        Console.WriteLine("Element: {0}", result2);

        // This commented part gives you exception
        // because the given sequence does not 
        // contain elements

        /*
            int[] sequence3 = {};
            var result3 = sequence3.Single();
            Console.WriteLine("Element: {0}", result3);
        */
    }
}
```

**Output:**

```cs
Element: 112
Element: 2

```

**例 2:**

```cs
// C# program to find the 
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

        // Query to find the name the 
        // employee Using Single method
        var res = emp.Single(e => e.emp_name == "Anjita");

        string val = res.emp_name;

        Console.WriteLine("Employee name: {0}", val);
    }
}
```

**Output:**

```cs
Employee name: Anjita

```