# LINQ中的OfType过滤操作符

> 原文：[https://www.geeksforgeeks.org/linq-filtering-operator-oftype/](https://www.geeksforgeeks.org/linq-filtering-operator-oftype/)

过滤运算符是那些用于根据给定数据源或给定序列的用户要求过滤数据的运算符。例如，在员工记录中，我们希望获得年龄在21岁的员工的数据。所以，我们根据他们的年龄过滤记录。在LINQ中，您可以使用以下运算符进行筛选：

1.  `Where`
2.  `OfType`

## OfType运算符

`OfType`运算符根据序列或数据源将集合中的元素强制转换为指定类型的能力来筛选序列或数据源。它是通过使用延迟执行来实现的，这意味着它会立即返回一个包含执行操作所需信息的对象，但是当该对象通过使用`foreach`循环或`for`循环在循环上迭代时，它就会执行。

- 在LINQ中，您可以在一个查询中使用多个`OfType`。
- 它在C#或VB.Net语言中不支持查询语法，但您可以使用方法语法，如下例所示。

### 示例1：查询语法

```cs
// C# program to illustrate the 
// concept of OfType operator
using System;
using System.Linq;
using System.Collections;

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

public class GFG {

    // Main method
    static public void Main()
    {

        // Data Source
        ArrayList myarray = new ArrayList();
        myarray.Add("GeeksforGeeks");
        myarray.Add(23);
        myarray.Add(new Employee() {emp_id = 209, emp_name = "Anjita"});
        myarray.Add(new Employee() {emp_id = 210, emp_name = "Soniya"});
        myarray.Add(new Employee() {emp_id = 300, emp_name = "Rohan"});

        // Using OfType operator
        var res1 = from e1 in myarray.OfType<string>()
                   select e1;

        foreach(var val1 in res1)
        {
            Console.WriteLine(val1);
        }

        var res2 = from e2 in myarray.OfType<Employee>()
                   select e2;

        foreach(var val2 in res2)
        {
            Console.WriteLine(val2.emp_name);
        }
    }
}
```

**输出：**

```cs
GeeksforGeeks
Anjita
Soniya
Rohan
```

- 它在C#或VB中支持方法语法。它在`Queryable`和`Enumerable`类中都可用。如下例所示。

### 示例2：方法语法

```cs
// C# program to illustrate the 
// concept of OfType operator
using System;
using System.Linq;
using System.Collections;

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

        // Data Source
        ArrayList myarray = new ArrayList();
        myarray.Add(new Employee() {emp_id = 209, emp_name = "Anjita"});
        myarray.Add(new Employee() {emp_id = 210, emp_name = "Soniya"});
        myarray.Add(new Employee() {emp_id = 300, emp_name = "Rohan"});

        // Get the id of the employees
        // Using OfType operator
        var res = myarray.OfType<Employee>();

        foreach(var val in res)
        {
            Console.WriteLine("Employee Id: {0}", val.emp_id);
        }
    }
}
```

**输出：**

```cs
Employee Id: 209
Employee Id: 210
Employee Id: 300
```