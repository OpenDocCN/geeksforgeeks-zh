# LINQ |集合操作员|联盟

> 原文:[https://www.geeksforgeeks.org/linq-set-operator-union/](https://www.geeksforgeeks.org/linq-set-operator-union/)

在 LINQ，集合运算符是查询表达式中返回结果集的运算符，该结果集基于相同或不同集合或序列或集合中等价元素的存在或不存在。标准查询运算符包含以下集合运算符:

1.  **工会**
2.  **相交**
3.  **除了**
4.  **不同**

#### 联盟

联合运算符返回集合联合。或者换句话说，我们可以说它返回包含出现在给定输入集合或序列中的唯一元素的集合。

![](img/dee4086b01bf5cefa48b595e9dcb94df.png)

*   它不支持 C# 和 VB.Net 语言中的查询语法。但是您可以对查询变量使用 Union 方法，或者您可以将查询包装在括号中，然后调用 Union 方法。
*   它支持 C# 和 VB.Net 语言中方法语法。
*   它同时出现在可查询类和可枚举类中。
*   它通过使用延迟执行来实现。
*   当您处理复杂类型的集合时，您必须使用 IEqualityComparer 接口，否则 Union 方法将给出不正确的结果。

**例 1:**

```cs
// C# program to find the union 
// of the given sequence
using System;
using System.Linq;

class GFG {

    static public void Main()
    {

        // Data source
        char[] sequence1 = {'m', 'q', 'o', 's', 'y', 'a'};
        char[] sequence2 = {'p', 't', 'r', 's', 'w', 'z'};

        // Display the sequences
        Console.WriteLine("Sequence 1 is: ");

        foreach(var s1 in sequence1)
        {
            Console.WriteLine(s1);
        }

        Console.WriteLine("Sequence 2 is: ");

        foreach(var s2 in sequence2)
        {
            Console.WriteLine(s2);
        }

        // Get union of the given sequence
        // Using Union function
        var result = sequence1.Union(sequence2);

        Console.WriteLine("Unique Sequence: ");

        foreach(var val in result)
        {
            Console.WriteLine(val);
        }
    }
}
```

**Output:**

```cs
Sequence 1 is: 
m
q
o
s
y
a
Sequence 2 is: 
p
t
r
s
w
z
Unique Sequence: 
m
q
o
s
y
a
p
t
r
w
z

```

**例 2:**

```cs
// C# program to find the common 
// languages known by the employees
using System;
using System.Linq;
using System.Collections.Generic;

// Employee details
public class Employee1 {

    public int emp_id1
    {
        get;
        set;
    }

    public string emp_name1
    {
        get;
        set;
    }
    public string emp_lang1
    {
        get;
        set;
    }
}
// Employee details
public class Employee2 {

    public int emp_id2
    {
        get;
        set;
    }

    public string emp_name2
    {
        get;
        set;
    }
    public string emp_lang2
    {
        get;
        set;
    }
}
public class GFG {

    // Main method
    static public void Main()
    {
        List<Employee1> emp1 = new List<Employee1>() {

            new Employee1() {emp_id1 = 209, emp_name1 = "Anjita",
                                               emp_lang1 = "C#"},

            new Employee1() {emp_id1 = 210, emp_name1 = "Soniya",
                                                emp_lang1 = "C"},

            new Employee1() {emp_id1 = 211, emp_name1 = "Rohit",
                                            emp_lang1 = "Java"},

        };

        List<Employee2> emp2 = new List<Employee2>() {

            new Employee2() {emp_id2 = 290, emp_name2 = "Anjita",
                                               emp_lang2 = "C#"},

            new Employee2() {emp_id2 = 212, emp_name2 = "MaMa", 
                                         emp_lang2 = "Python"},

            new Employee2() {emp_id2 = 233, emp_name2 = "Rima", 
                                           emp_lang2 = "Java"},

        };

        // Query to find the common languages
        // known by the employees
        // Using Union method
        var res = emp1.Select(e => e.emp_lang1).Union(emp2.Select(e => e.emp_lang2));

        Console.WriteLine("Common Languages: ");

        foreach(var val in res)
        {
            Console.WriteLine(val);
        }
    }
}
```

**Output:**

```cs
Common Languages: 
C#
C
Java
Python

```