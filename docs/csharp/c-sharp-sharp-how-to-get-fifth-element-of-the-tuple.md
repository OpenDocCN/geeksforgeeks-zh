# C# |如何获取元组的第五元素？

> 原文:[https://www . geeksforgeeks . org/c-sharp-sharp-如何获取元组的第五个元素/](https://www.geeksforgeeks.org/c-sharp-sharp-how-to-get-fifth-element-of-the-tuple/)

**[Tuple](https://www.geeksforgeeks.org/c-sharp-tuple/)** 是一种数据结构，它为您提供了最简单的方法来表示具有多个值的数据集，这些值可能彼此相关，也可能彼此不相关。 **Item5 属性**用于获取给定元组的第五个元素。它不适用于 1 元组、2 元组、3 元组和 4 元组，但适用于所有其他剩余元组。

**语法:**

```cs
public T5 Item5 { get; }
```

这里， *T5* 是当前 Tuple < >对象的第五个分量的值。这个元组< >可以是 5 元组，或者 6 元组，或者 7 元组，或者 8 元组。

**示例:**在下面的代码中，您可以看到我们正在访问每个元组的第五个元素。

```cs
// C# program to illustrate how to get 
// the fifth element of the tuple
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Taking 5-tuple
        var st5 = Tuple.Create("Siya", 22, "EEE", 2017,
                                           "20-Mar-1993");

        Console.WriteLine("Student-5 DOB: " + st5.Item5);

        // Taking 6-tuple
        var st6 = Tuple.Create("Riya", 24, "ME", 2015,
                               "30-May-1991", 230134832);

        Console.WriteLine("Student-6 DOB: " + st6.Item5);

        // Taking 7-tuple
        var st7 = Tuple.Create("Rohit", 21, "IT", 2017, 
                        "21-Apr-1994", 384749829, 20000);

        Console.WriteLine("Student-7 DOB: " + st7.Item5);

        // Taking 8-tuple
        var st8 = Tuple.Create("Manita", 24, "CSE", 2013, 
                   "03-Aug-1991", 235678909, 34000, "C#");

        Console.WriteLine("Student-8 DOB: " + st8.Item5);
    }
}
```

**输出:**

```cs
Student-5 DOB: 20-Mar-1993
Student-6 DOB: 30-May-1991
Student-7 DOB: 21-Apr-1994
Student-8 DOB: 03-Aug-1991

```