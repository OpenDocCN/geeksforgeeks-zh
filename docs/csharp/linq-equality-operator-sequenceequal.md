# LINQ |等式运算符|顺序等式

> 原文:[https://www . geesforgeks . org/linq-equality-operator-sequence eqal/](https://www.geeksforgeeks.org/linq-equality-operator-sequenceequal/)

相等运算符用于检查给定的两个序列是否相等。在 LINQ，等式运算只包含一个称为*序列等式*的运算符。它用于检查序列或集合中的给定元素是否相等。如果给定的序列或集合相等，则返回*真*否则返回*假*。

*   如果集合或序列具有基本数据类型，它将比较值和元素的数量。
*   如果集合包含复杂类型的元素，它将检查对象的引用。
*   它不支持 C# 和 VB.Net 语言中的查询语法。
*   它支持 C# 和 VB.Net 语言中方法语法。
*   它同时出现在可查询类和可枚举类中。
*   它通过使用延迟执行来实现。
*   您可以使用 IEqualityComparer 类来比较两个复杂类型的集合。

**例 1:**

```cs
// C# program to check the given
// sequences are equal or not
using System;
using System.Linq;

class GFG {

    static public void Main()
    {

        // Data source
        char[] sequence1 = {'p', 'q', 'r', 's', 'y', 'z'};
        char[] sequence2 = {'p', 'q', 'r', 's', 'y', 'z'};

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

        // Check the given sequences are equal or 
        // not Using SequenceEqual function
        var result = sequence1.SequenceEqual(sequence2);
        Console.WriteLine("Given Sequences are equal: {0}", result);
    }
}
```

**Output:**

```cs
Sequence 1 is: 
p
q
r
s
y
z
Sequence 2 is: 
p
q
r
s
y
z
Given Sequences are equal: True

```

**例 2:**

```cs
// C# program to check the names of
// the employee are equal or not
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

            new Employee2() {emp_id2 = 209, emp_name2 = "Anjita",
                                            emp_lang2 = "Scala"},

            new Employee2() {emp_id2 = 210, emp_name2 = "Soniya",
                                           emp_lang2 = "Python"},

            new Employee2() {emp_id2 = 211, emp_name2 = "Rohit",
                                            emp_lang2 = "Ruby"},

        };

        // Query to check the names of
        // the employee are equal or not
        // Using SequenceEqual method
        var res = emp1.Select(e => e.emp_name1).SequenceEqual(emp2.Select(e => e.emp_name2));

        Console.WriteLine(res);
    }
}
```

**Output:**

```cs
True

```