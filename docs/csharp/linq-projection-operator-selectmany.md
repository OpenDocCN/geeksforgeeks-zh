# LINQ |投影操作员|选择多个

> 原文:[https://www . geesforgeks . org/linq-project-operator-selectmany/](https://www.geeksforgeeks.org/linq-projection-operator-selectmany/)

在 LINQ，投影是一种将物体转换成新形式的操作，新形式只保留那些随后将被使用的属性。通过使用投影，开发人员可以创建一个由每个对象构建的新类型。你可以投射属性并对其进行数学函数运算，也可以投射原始对象而不进行变换。

在 LINQ，可以进行以下投影操作:

1.  **选择**
2.  **选取多个**

#### 选择多个运算符

SelectMany 运算符返回基于转换函数的值序列，然后将它们组合成一个序列。或者换句话说，我们可以说，当您想要从多个集合中选择值时，或者如果您想要从列表列表中选择一个结果并想要显示为单个序列时，将使用 SelectMany 运算符。

**查询语法中的选择多:**在查询语法中，选择多运算符的工作是通过使用多个 from 子句来实现的。如下例所示。

**示例:**

```cs
// C# program to find the languages
// known by the employee
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
    public List<string> emp_lang
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
            new Employee() {emp_id = 209, emp_name = "Anjita", emp_gender = "Female", emp_hire_date = "12/3/2017", emp_salary = 20000, emp_lang = new List<string>{"C#", "VB"} },
                new Employee() {emp_id = 210, emp_name = "Soniya", emp_gender = "Female", emp_hire_date = "22/4/2018", emp_salary = 30000,  emp_lang = new List<string>{ "Java"} },
                new Employee() {emp_id = 211, emp_name = "Rohit", emp_gender = "Male", emp_hire_date = "3/5/2016", emp_salary = 40000,  emp_lang = new List<string>{ "C++", "SQL"} },
                new Employee() {emp_id = 212, emp_name = "Supriya", emp_gender = "Female", emp_hire_date = "4/8/2017", emp_salary = 40000,  emp_lang = new List<string>{"Python", "C", "PHP"} },
                new Employee() {emp_id = 213, emp_name = "Anil", emp_gender = "Male", emp_hire_date = "12/1/2016", emp_salary = 40000,  emp_lang = new List<string>{"HTML", "JQuery"} },
                new Employee() {emp_id = 214, emp_name = "Anju", emp_gender = "Female", emp_hire_date = "17/6/2015", emp_salary = 50000,  emp_lang = new List<string>{"JavaScript", "Perl"} },
        };

        // Query to find the languages
        // known by the employee
        var res = from e in emp
                      from e2 in e.emp_lang
                          select e2;

        Console.WriteLine("Languages known by all the employees are:");
        foreach(var val in res)
        {
            Console.WriteLine(val);
        }
    }
}
```

**Output:**

```cs
Languages known by all the employees are:
C#
VB
Java
C++
SQL
Python
C
PHP
HTML
JQuery
JavaScript
Perl

```

**方法语法中的选择许多:**选择许多方法存在于可查询类和可枚举类中，并且受到 C# 和 VB.Net 语言的支持。

**示例:**

```cs
// C# program to find the languages
// known by the employee
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
    public List<string> emp_lang
    {
        get;
        set;
    }
}

public class GFG {

    // Main method
    static public void Main()
    {
        List<Employee> emp = new List<Employee>() {
            new Employee() {emp_id = 209, emp_name = "Anjita", emp_gender = "Female", emp_hire_date = "12/3/2017", emp_salary = 20000, emp_lang = new List<string>{"C#", "VB"} },
                new Employee() {emp_id = 210, emp_name = "Soniya", emp_gender = "Female", emp_hire_date = "22/4/2018", emp_salary = 30000,  emp_lang = new List<string>{ "Java"} },
                new Employee() {emp_id = 211, emp_name = "Rohit", emp_gender = "Male", emp_hire_date = "3/5/2016", emp_salary = 40000,  emp_lang = new List<string>{ "C++", "SQL"} },
                new Employee() {emp_id = 212, emp_name = "Supriya", emp_gender = "Female", emp_hire_date = "4/8/2017", emp_salary = 40000,  emp_lang = new List<string>{"Python", "C", "PHP"} },
                new Employee() {emp_id = 213, emp_name = "Anil", emp_gender = "Male", emp_hire_date = "12/1/2016", emp_salary = 40000,  emp_lang = new List<string>{"HTML", "JQuery"} },
                new Employee() {emp_id = 214, emp_name = "Anju", emp_gender = "Female", emp_hire_date = "17/6/2015", emp_salary = 50000,  emp_lang = new List<string>{"JavaScript", "Perl"} },
        };

        // Finding the languages known by the employee
        // Using SelectMany method
        var res = emp.SelectMany(a => a.emp_lang);
        Console.WriteLine("Languages known by all the employees are:");
        foreach(var val in res)
        {
            Console.WriteLine(val);
        }
    }
}
```

**Output:**

```cs
Languages known by all the employees are:
C#
VB
Java
C++
SQL
Python
C
PHP
HTML
JQuery
JavaScript
Perl

```