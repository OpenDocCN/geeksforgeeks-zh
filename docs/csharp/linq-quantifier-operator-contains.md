# LINQ |量词运算符|包含

> 原文:[https://www . geesforgeks . org/linq-量词-运算符-contains/](https://www.geeksforgeeks.org/linq-quantifier-operator-contains/)

在 LINQ，量词运算符用于返回一个布尔值，该值表明某些或所有元素是否满足给定条件。标准查询运算符支持 3 种不同类型的量词运算符:

1.  **全部**
2.  **任意**
3.  **包含**

#### 包含运算符

Contains 运算符用于检查给定的序列或集合是否包含指定的元素。如果给定的序列包含指定的元素，它将返回 true，否则返回 false。它以两种不同的类型重载:

*   **包含<源> (IEnumerable <源>，源:**此方法用于通过使用默认的相等比较器来检查序列是否包含指定的元素。
*   **包含<源> (IEnumerable <源>、源、IEqualitcomparer<源> ):** 此方法用于使用指定的 IEqualitcomparer 检查序列是否包含指定的元素。

**要点:**

*   它不支持 C# 和 VB.Net 语言中的查询语法。
*   它支持 C# 和 VB.Net 语言中方法语法。
*   它同时出现在可查询类和可枚举类中。
*   如果给定的源为空，它将引发 ArgumentNullException。
*   它不返回值，而是返回真或假。
*   该操作员的返回类型为*系统。布尔*。
*   您可以使用自定义类来检查给定集合中的对象，该类将 IEqualityOperator 派生为 Contains。

**例 1:**

```cs
// C# program to illustrate the
// use of Contains operator
using System;
using System.Linq;
using System.Collections.Generic;

class GFG {

    static public void Main()
    {

        // Data source
        int[] sequence1 = {34, 56, 77, 88,
                          99, 10, 23, 46};

        string[] sequence2 = {"Geek", "Geeks123",
                                "GeeksforGeeks"};

        // Check the sequence1 contain 10
        // Using Contains operator
        var result1 = sequence1.Contains(10);

        Console.WriteLine("Result: {0}", result1);

        // Check the sequence2 contain "qq"
        // Using Contains operator
        var result2 = sequence2.Contains("123Geek");

        Console.WriteLine("Result: {0}", result2);
    }
}
```

**Output:**

```cs
Result: True
Result: False

```

**例 2:**

```cs
// C# program to check the new employee
// is found in the given old data list
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

// the EmpCompar class implements
// IEqualityComparer<Employee>
// To compare the details of the new 
// employee to the details of the old list
public class EmpCompar : IEqualityComparer<Employee> {

    public bool Equals(Employee a, Employee b)
    {
        if (a.emp_id == b.emp_id && a.emp_name == b.emp_name &&
                                a.emp_gender == b.emp_gender && 
                          a.emp_hire_date == b.emp_hire_date && 
                                  a.emp_salary == b.emp_salary)
            return true;

        return false;
    }

    public int GetHashCode(Employee obj)
    {
        return obj.GetHashCode();
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

        // New employee
        Employee emp1 = new Employee() {emp_id = 215, emp_name = "Anu",
                    emp_gender = "Female", emp_hire_date = "18/6/2015",
                                                   emp_salary = 50000};

        // Query to check the new employee is 
        // found in the given old data list
        // Using Contain operator
        var res = emp.Contains(emp1, new EmpCompar());
        Console.WriteLine("Employee Found?: {0}", res);
    }
}
```

**Output:**

```cs
Employee Found?: False

```