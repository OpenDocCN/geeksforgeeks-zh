# LINQ |元素运算符|第一个命令默认

> 原文:[https://www . geesforgeks . org/linq-element-operator-first ordefault/](https://www.geeksforgeeks.org/linq-element-operator-firstordefault/)

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

#### 第一个默认运算符

FirstOrDefault 运算符用于返回给定集合或序列的第一个元素。或者也可以根据给定的条件返回第一个元素。如果给定的集合或序列不包含任何元素，或者如果集合或序列不包含指定给定条件的元素，则提供默认值。或者我们可以说，创建 FirstOrDefault 运算符是为了克服 First 运算符的*invalid operationexception*问题。该方法可以通过两种不同的方式重载:

*   **first orderefault<t source>(IEnumerable<t source>):**这个方法返回给定序列或集合的第一个元素，没有任何条件。或者如果给定的集合或序列不包含任何元素，则返回默认值。
*   **first orderefault<t source>(IEnumerable<t source>，Func < TSource，Boolean > ):** 此方法返回指定给定条件的第一个元素。或者如果集合不包含指定给定条件的元素，则返回默认值。

**要点:**

*   它不支持 C# 和 VB.Net 语言中的查询语法。
*   它支持 C# 和 VB.Net 语言中方法语法。
*   它同时出现在可查询类和可枚举类中。
*   如果给定集合包含空元素，则此方法将引发 ArgumentNullException。
*   引用类型和可空类型的默认值为 null。

**例 1:**

```cs
// C# program to illustrate the 
// use of FirstOrDefault operator
using System;
using System.Linq;
using System.Collections.Generic;

class GFG {

    static public void Main()
    {

        // Data source
        int[] sequence1 = {112, 44, 55,
                      66, 77, 777, 56};

        // Get the element which specifies
        // the given condition
        // Using FirstOrDefault function
        var result1 = sequence1.FirstOrDefault(seq => seq < 77);

        Console.WriteLine("Value: {0}", result1);

        // Getting Default value because the
        // sequence does not contain any element
        int[] sequence2 = {};

        var result2 = sequence2.FirstOrDefault();

        Console.WriteLine("Default value: {0}", result2);
    }
}
```

**Output:**

```cs
Value: 44
Default value: 0

```

**例 2:**

```cs
// C# program to find the name 
// of the first employee
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

        // Query to find the name the first 
        // employee Using FirstOrDefault method
        var res = emp.Select(e => e.emp_name).FirstOrDefault();

        Console.WriteLine("Employee Name: {0}", res);
    }
}
```

**Output:**

```cs
Employee Name: Anjita

```