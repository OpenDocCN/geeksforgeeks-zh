# C# |如何获取元组的剩余元素？

> 原文:[https://www . geeksforgeeks . org/c-sharp-如何获取元组的剩余元素/](https://www.geeksforgeeks.org/c-sharp-how-to-get-the-remaining-elements-of-the-tuple/)

**[Tuple](https://www.geeksforgeeks.org/c-sharp-tuple/)** 是一种数据结构，它为您提供了最简单的方法来表示具有多个值的数据集，这些值可能彼此相关，也可能彼此不相关。我们知道，通过使用*项<元素编号>* 属性，我们可以获得元组中存在的元素，但是该属性仅适用于七个元素。如果你想得到剩余的元素，那么你必须去**休息**属性。

Rest 属性允许您获取元组的剩余元素，而不是开始的七个元素。

**语法:**

```cs
public TRest Rest { get; }
```

这里， *TRest* 是当前*元组< T1、T2、T3、T4、T5、T6、T7、TRest >* 对象剩余组件的值。

**示例:**

```cs
// C# program to illustrate the 
// concept of Rest property
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // Creating 8-tuple
        var stu = Tuple.Create("Mohan", 24, "CSE", 2016,
                               209, 235678909, "C#", 1);

        // Accessing first element
        Console.WriteLine("Student Name: " + stu.Item1);

        // Accessing Second element
        Console.WriteLine("Student Age: " + stu.Item2);

        // Accessing third element
        Console.WriteLine("Student Branch: " + stu.Item3);

        // Accessing fourth element
        Console.WriteLine("Student Passing Year: " + stu.Item4);

        // Accessing fifth element
        Console.WriteLine("Student Id: " + stu.Item5);

        // Accessing sixth element
        Console.WriteLine("Student Contact Number: " + stu.Item6);

        // Accessing seventh element
        Console.WriteLine("Student Fav Programming Language: " + stu.Item7);

        // Accessing remaining element
        // Using Rest property
        Console.WriteLine("Student Rank: " + stu.Rest);
    }
}
```

**Output:**

```cs
Student Name: Mohan
Student Age: 24
Student Branch: CSE
Student Passing Year: 2016
Student Id: 209
Student Contact Number: 235678909
Student Fav Programming Language: C#
Student Rank: (1)

```

**注意:**还可以使用 Rest 属性获取嵌套元组的元素。

**示例:**

```cs
// C# program to illustrate how to access 
// nested tuple using Rest property
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // Creating 8-tuple
        var stu = Tuple.Create("Guriya", 24, "CSE", 2016, 209, 235678909,
                         1, Tuple.Create("C#", "C++", "Java", "Python"));

        // Accessing first element
        Console.WriteLine("Student Name: " + stu.Item1);

        // Accessing Second element
        Console.WriteLine("Student Age: " + stu.Item2);

        // Accessing third element
        Console.WriteLine("Student Branch: " + stu.Item3);

        // Accessing fourth element
        Console.WriteLine("Student Passing Year: " + stu.Item4);

        // Accessing fifth element
        Console.WriteLine("Student Id: " + stu.Item5);

        // Accessing sixth element
        Console.WriteLine("Student Contact Number: " + stu.Item6);

        // Accessing seventh element
        Console.WriteLine("Student Rank: " + stu.Item7);

        // Accessing remaining element
        // or accessing the elements of nested tuple
        // Using Rest property
        Console.WriteLine("Student Fav. Programming Language: " + stu.Rest);
    }
}
```

**Output:**

```cs
Student Name: Guriya
Student Age: 24
Student Branch: CSE
Student Passing Year: 2016
Student Id: 209
Student Contact Number: 235678909
Student Rank: 1
Student Fav. Programming Language: ((C#, C++, Java, Python))

```