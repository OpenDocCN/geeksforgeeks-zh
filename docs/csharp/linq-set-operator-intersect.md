# LINQ |集合运算符|交集

> 原文:[https://www.geeksforgeeks.org/linq-set-operator-intersect/](https://www.geeksforgeeks.org/linq-set-operator-intersect/)

在 LINQ，集合运算符是查询表达式中返回结果集的运算符，该结果集基于相同或不同集合或序列或集合中等价元素的存在或不存在。标准查询运算符包含以下集合运算符:

1.  **工会**
2.  **相交**
3.  **除了**
4.  **不同**

#### 相交运算符

交集运算符返回集合交集。或者换句话说，我们可以说它返回的集合或集合中包含的公共元素出现在两个集合或集合中。

![](img/b805c9c7892028761a7f229c2adecbea.png)

*   它不支持 C# 和 VB.Net 语言中的查询语法。但是您可以对查询变量使用 Intersect 方法，或者您可以将查询包装在括号中，然后调用 Intersect 方法。
*   它支持 C# 和 VB.Net 语言中方法语法。
*   它同时出现在可查询类和可枚举类中。
*   它通过使用延迟执行来实现。
*   当您处理复杂类型的集合时，必须使用 IEqualityComparer 接口，否则 Intersect 方法会给出不正确的结果。

**例 1:**

```cs
// C# program to find the intersection
// of the given sequence
using System;
using System.Linq;

class GFG {

    static public void Main()
    {

        // Data source
        char[] sequence1 = {'m', 'q', 'o',
                           's', 'y', 'a'};

        char[] sequence2 = {'p', 't', 'r', 
                           's', 'y', 'z'};

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

        // Get intersection of the given sequence
        // Using Intersect function
        var result = sequence1.Intersect(sequence2);

        Console.WriteLine("New Sequence: ");

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
y
z
New Sequence: 
s
y

```

**例 2:**

```cs
// C# program to find the commonly
// known languages by the employees
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

        // Query to find the commonly known
        // languages by the employees
        // Using Intersect method
        var res = emp1.Select(e => e.emp_lang1).Intersect(emp2.Select(e => e.emp_lang2));

        Console.WriteLine("Commonly known Languages: ");

        foreach(var val in res)
        {
            Console.WriteLine(val);
        }
    }
}
```

**Output:**

```cs
Commonly known Languages: 
C#
Java

```