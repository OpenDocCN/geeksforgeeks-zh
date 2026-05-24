# LINQ |发电运营商| defaultifmpty

> 原文:[https://www . geeksforgeeks . org/linq-generation-operator-defaultifmpty/](https://www.geeksforgeeks.org/linq-generation-operator-defaultifempty/)

生成运算符用于创建新的值序列。标准查询运算符支持 **4** 种不同类型的生成运算符:

1.  **default ifying**
2.  **清空**
3.  **范围**
4.  **重复**

#### 默认女性操作符

DefaultIfEmpty 运算符用于将空集合或序列替换为缺省值的单例集合或序列。或者换句话说，如果源为空，它返回一个带有默认值的集合或序列，否则返回源。

*   该运算符以两种不同的方式重载:
    *   **defaultifmpty<t source>(IEnumerable<t source>，t source:**如果序列为空，此方法用于返回单例集合中指定序列或指定值的元素。
    *   **defaultifmpty<t source>(IEnumerable<t source>):**如果序列为空，此方法用于返回单例集合中指定序列的元素或类型参数的默认值。
*   它不支持 C# 和 VB.Net 语言中的查询语法。
*   它支持 C# 和 VB.Net 语言中方法语法。
*   它同时出现在可查询类和可枚举类中。
*   它通过使用延迟执行来实现。
*   如果给定的源为空，defaultifmpty<tsource>(IEnumerable<tsource>)将返回 *ArgumentNullException* 。</tsource></tsource>
*   引用类型和可空类型的默认值为 null。

**例 1:**

```cs
// C# program to illustrate the
// use of DefaultIfEmpty operator
using System;
using System.Linq;
using System.Collections.Generic;

class GFG {

    static public void Main()
    {

        // Data source 1
        int[] sequence1 = {};

        // The sequence is empty so it 
        // will return the default value
        // Using DefaultIfEmpty
        foreach(var val1 in sequence1.DefaultIfEmpty())
        {
            Console.WriteLine(val1);
        }

        // Data source 2
        string[] sequence2 = {"Geek", "Geeks123",
                                "GeeksforGeeks"};

        // The given sequence 2 is non-empty so 
        // it will return the sequence
        // Using DefaultIfEmpty
        foreach(var val2 in sequence2.DefaultIfEmpty())
        {
            Console.WriteLine(val2);
        }
    }
}
```

**Output:**

```cs
0
Geek
Geeks123
GeeksforGeeks

```

**例 2:**

```cs
// C# program to illustrate the 
// use of DefaultIfEmpty operator
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

        // Using DefaultIfEmpty operator
        foreach(Employee e in emp.DefaultIfEmpty())
        {
            Console.WriteLine(e.emp_name);
        }
    }
}
```

**Output:**

```cs
Anjita
Soniya
Rohit
Supriya
Anil
Anju

```