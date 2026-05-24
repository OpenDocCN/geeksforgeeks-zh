# 如何在 C# 中获取嵌套 ValueTuple 的元素？

> 原文:[https://www . geeksforgeeks . org/如何获取 c-sharp 中嵌套值元组的元素/](https://www.geeksforgeeks.org/how-to-get-the-elements-of-the-nested-valuetuple-in-c-sharp/)

[ValueTuple](https://www.geeksforgeeks.org/valuetuple-in-c-sharp/) 是 C# 7.0 中引入的一个结构，代表值类型 Tuple。它允许您存储包含多个值的数据集，这些值可能彼此相关，也可能彼此不相关。我们知道*项<元素编号>* 属性用于获取值元组中存在的元素，但该属性仅适用于七个元素。如果你想得到剩余的元素，那么你必须去**休息属性**。
Rest 属性允许您获取值元组的剩余元素，而不是开始的七个元素。或者，您可以说它用于访问嵌套值元组的元素。

**语法:**

```cs
public TRest Rest;
```

这里，TRest 是 ValueTuple <t1 t2="" t3="" t4="" t5="" t6="" t7="" trest="">结构的字段值。</t1>

**例 1:**

```cs
// C# program to illustrate how to get
// the eigth element of value tuple
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // Creating a value tuple with eight elements
        var ValTpl = ValueTuple.Create("Methods", "Method Hiding",
                        "Optional Parameters", "Anonymous Method",
                              "Partial Methods", "Local Function",
                                      "Delegates", "Destructors");

        Console.WriteLine("C# Topics: ");

        // Accessing the first element of 8-ValueTuple
        // Using Item property
        Console.WriteLine(ValTpl.Item1);

        // Accessing the second element of 8-ValueTuple
        // Using Item property
        Console.WriteLine(ValTpl.Item2);

        // Accessing the third element of 8-ValueTuple
        // Using Item property
        Console.WriteLine(ValTpl.Item3);

        // Accessing the fourth element of 8-ValueTuple
        // Using Item property
        Console.WriteLine(ValTpl.Item4);

        // Accessing the fifth element of 8-ValueTuple
        // Using Item property
        Console.WriteLine(ValTpl.Item5);

        // Accessing the sixth element of 8-ValueTuple
        // Using Item property
        Console.WriteLine(ValTpl.Item6);

        // Accessing the seventh element of 8-ValueTuple
        // Using Item property
        Console.WriteLine(ValTpl.Item7);

        // Accessing the eighth element of 8-ValueTuple
        // Using Rest property
        Console.WriteLine(ValTpl.Rest);
    }
}
```

**Output:**

```cs
C# Topics: 
Methods
Method Hiding
Optional Parameters
Anonymous Method
Partial Methods
Local Function
Delegates
(Destructors)

```

**例 2:**

```cs
// C# program to get the
// elements of nested value tuple
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Creating a nested value tuple
        // Using ValueTuple<T1, T2, T3, T4, T5, T6,
        // T7, TRest>(T1, T2, T3, T4, T5, T6, T7, 
        // TRest rest) constructor
        var MyValTpl = ValueTuple.Create(23456, "Anu", "CSE", "14-4-1992",
                   27, 2010, 3456781234, ValueTuple.Create("Java", "C#"));

        // Accessing the elements of the value tuple
        Console.WriteLine("Employee Details:");
        Console.WriteLine("Id: {0}", MyValTpl.Item1);
        Console.WriteLine("Name: {0}", MyValTpl.Item2);
        Console.WriteLine("Branch: {0}", MyValTpl.Item3);
        Console.WriteLine("DOB: {0}", MyValTpl.Item4);
        Console.WriteLine("Age: {0}", MyValTpl.Item5);
        Console.WriteLine("Passing Year: {0}", MyValTpl.Item6);
        Console.WriteLine("Phone Number: {0}", MyValTpl.Item7);
        Console.WriteLine("Programming Language: {0}", MyValTpl.Rest);
    }
}
```

**Output:**

```cs
Employee Details:
Id: 23456
Name: Anu
Branch: CSE
DOB: 14-4-1992
Age: 27
Passing Year: 2010
Phone Number: 3456781234
Programming Language: ((Java, C#))

```