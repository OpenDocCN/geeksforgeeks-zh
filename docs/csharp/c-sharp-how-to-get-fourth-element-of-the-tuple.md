# C# |如何获取元组的第四个元素？

> 原文:[https://www . geeksforgeeks . org/c-sharp-如何获取元组中的第四个元素/](https://www.geeksforgeeks.org/c-sharp-how-to-get-fourth-element-of-the-tuple/)

**[Tuple](https://www.geeksforgeeks.org/c-sharp-tuple/)** 是一种数据结构，它为您提供了最简单的方法来表示具有多个值的数据集，这些值可能彼此相关，也可能彼此不相关。 **Item4 属性**用于获取给定元组的第四个元素。它不适用于 1 元组、2 元组和 3 元组，但适用于所有其他剩余元组。

**语法:**

```cs
public T4 Item4 { get; }
```

这里， *T4* 是当前 Tuple < >对象的第四个分量的值。这个元组< >可以是 4 元组，或 5 元组，或 6 元组，或 7 元组，或 8 元组。

**示例:**在下面的代码中，可以看到我们正在访问每个元组的第四个元素。

```cs
// C# program to illustrate how to get 
// the fourth element of the tuple
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Taking 4-tuple
        var st4 = Tuple.Create("Rohan", 29, "EC", 2015);
        Console.WriteLine("Student-4 Year: " + st4.Item4);

        // Taking 5-tuple
        var st5 = Tuple.Create("Siya", 22, "EEE", 2017,
                                           "20-Mar-1993");

        Console.WriteLine("Student-5 Year: " + st5.Item4);

        // Taking 6-tuple
        var st6 = Tuple.Create("Riya", 24, "ME", 2015,
                               "30-May-2015", 230134832);

        Console.WriteLine("Student-6 Year: " + st6.Item4);

        // Taking 7-tuple
        var st7 = Tuple.Create("Rohit", 21, "IT", 2017, 
                        "21-Apr-1998", 384749829, 20000);

        Console.WriteLine("Student-7 Year: " + st7.Item4);

        // Taking 8-tuple
        var st8 = Tuple.Create("Manita", 24, "CSE", 2016, 
                   "03-Aug-1991", 235678909, 34000, "C#");

        Console.WriteLine("Student-8 Year: " + st8.Item4);
    }
}
```

**Output:**

```cs
Student-4 Year: 2015
Student-5 Year: 2017
Student-6 Year: 2015
Student-7 Year: 2017
Student-8 Year: 2016

```