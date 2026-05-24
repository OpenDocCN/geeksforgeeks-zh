# LINQ |分区操作员| SkipWhile

> 原文:[https://www . geesforgeks . org/linq-partition-operator-skiphile/](https://www.geeksforgeeks.org/linq-partition-operator-skipwhile/)

在 LINQ，分区运算符用于将给定的序列分成两部分，而无需对元素进行排序，并返回其中一部分。标准查询运算符支持 **4** 种不同类型的分区运算符:

1.  **跳过**
2.  **滑行同时**
3.  **取**
4.  **趁**

#### 当操作员

SkipWhile 运算符用于根据谓词函数跳过元素，直到给定序列中的元素不满足给定条件，然后返回剩余的元素。*这个方法有两种不同的重载方式:*

*   **skip while<t source>(IEnumerable<t source>，Func < TSource，Boolean > ):** 只要指定条件为真，该方法用于绕过给定序列中的元素，然后返回剩余的元素。
*   **skip while<t source>(IEnumerable<t source>，Func < TSource，Int32，Boolean > ):** 该方法用于在指定条件为真的情况下绕过给定序列中的元素，然后返回剩余的元素。元素的索引用于谓词函数的逻辑中。

**要点:**

*   它不支持 C# 和 VB.Net 语言中的查询语法。但是您可以使用 SkipWhile 方法来查询变量，或者您可以将查询包装在括号中，然后调用 SkipWhile 方法。
*   它支持 C# 和 VB.Net 语言中方法语法。
*   它同时出现在可查询类和可枚举类中。
*   它通过使用延迟执行来实现。
*   如果源或条件为空，它将引发 ArgumentNullException。

**例 1:**

```cs
// C# program to illustrate the
// concept of SkipWhile operator
using System;
using System.Linq;

class GFG {

    static public void Main()
    {

        // Data source
        int[] sequence = {45, 67, 89, 13,
                             56, 76, 67};

        // Query which skips the 
        // elements lesser than 67
        // Using SkipWhile method
        var result = sequence.OrderBy(s => s).SkipWhile(s => s < 67);
        Console.WriteLine("Sequence: ");

        // Display new sequence
        foreach(var val in result)
        {
            Console.WriteLine(val);
        }
    }
}
```

**Output:**

```cs
Sequence: 
67
67
76
89

```

**例 2:**

```cs
// C# program to find the names of the
// employees whose length is less than 4
using System; 
using System.Linq; 
using System.Collections.Generic; 

// Employee details 
public class Employee { 

    public int emp_id{get; set;} 
    public string emp_name{get; set;} 
    public string emp_gender{get; set;} 
    public string emp_hire_date{get; set;} 
    public int emp_salary{get; set;} 

} 

public class GFG{ 

    // Main method 
    static public void Main (){ 

    List<Employee> emp = new List<Employee>(){ 

        new Employee(){emp_id = 209, emp_name = "Anjita", emp_gender = "Female", 
                               emp_hire_date = "12/3/2017", emp_salary = 20000}, 

        new Employee(){emp_id = 210, emp_name = "Soniya", emp_gender = "Female", 
                               emp_hire_date = "22/4/2018", emp_salary = 30000}, 

        new Employee(){emp_id = 211, emp_name = "Rohit", emp_gender = "Male", 
                             emp_hire_date = "3/5/2016", emp_salary = 40000}, 

        new Employee(){emp_id = 212, emp_name = "Anu", emp_gender = "Female", 
                             emp_hire_date = "4/8/2017", emp_salary = 80000}, 

        new Employee(){emp_id = 213, emp_name = "Anil", emp_gender = "Male", 
                           emp_hire_date = "12/1/2016", emp_salary = 60000}, 

        new Employee(){emp_id = 214, emp_name = "Anju", emp_gender = "Female", 
                             emp_hire_date = "17/6/2015", emp_salary = 50000}, 
    }; 

    // Query to find the names of the
    // employees whose length are less
    // than 4 Using SkipWhile method
    var res = emp.SkipWhile(e=> e.emp_name.Length > 4);

    foreach(var val in res) 
    { 
        Console.WriteLine("Employee Name: {0}",
                                 val.emp_name); 
    } 

    } 
} 
```

**Output:**

```cs
Employee Name: Anu
Employee Name: Anil
Employee Name: Anju

```