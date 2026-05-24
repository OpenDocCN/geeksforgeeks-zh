# C# |如何获取元组的第一个元素？

> 原文:[https://www . geeksforgeeks . org/c-sharp-如何获取元组中的第一个元素/](https://www.geeksforgeeks.org/c-sharp-how-to-get-first-element-of-the-tuple/)

**[Tuple](https://www.geeksforgeeks.org/c-sharp-tuple/)** 是一种数据结构，它为您提供了最简单的方法来表示具有多个值的数据集，这些值可能彼此相关，也可能彼此不相关。 **Item1 属性**用于获取给定元组的第一个元素。它适用于每个元组，如 1 元组、2 元组等。

**语法:**

```cs
public T1 Item1 { get; }
```

这里， *T1* 是当前 Tuple < >对象的第一个分量的值。这个元组< >可以是 1 元组、2 元组、3 元组、4 元组、5 元组、6 元组、7 元组或 8 元组。

**示例:**在下面的代码中，可以看到我们正在访问每个元组的第一个元素。

```cs
// C# program to illustrate how to get 
// the first element of the tuple
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Taking 1-tuple
        var st1 = Tuple.Create("Mohan");
        Console.WriteLine("Student-1 Name: " + st1.Item1);

        // Taking 2-tuple
        var st2 = Tuple.Create("Sohan", 20);
        Console.WriteLine("Student-2 Name: " + st2.Item1);

        // Taking 3-tuple
        var st3 = Tuple.Create("Soniya", 30, "CSE");
        Console.WriteLine("Student-3 Name: " + st3.Item1);

        // Taking 4-tuple
        var st4 = Tuple.Create("Rohan", 29, "CSE", 2015);
        Console.WriteLine("Student-4 Name: " + st4.Item1);

        // Taking 5-tuple
        var st5 = Tuple.Create("Siya", 22, "CSE", 2017,
                                           "20-Mar-1993");

        Console.WriteLine("Student-5 Name: " + st5.Item1);

        // Taking 6-tuple
        var st6 = Tuple.Create("Riya", 24, "CSE", 2015,
                               "30-May-2015", 230134832);

        Console.WriteLine("Student-6 Name: " + st6.Item1);

        // Taking 7-tuple
        var st7 = Tuple.Create("Rohit", 21, "CSE", 2017, 
                        "21-Apr-1998", 384749829, 20000);

        Console.WriteLine("Student-7 Name: " + st7.Item1);

        // Taking 8-tuple
        var st8 = Tuple.Create("Manita", 24, "CSE", 2016, 
                   "03-Aug-1991", 235678909, 34000, "C#");

        Console.WriteLine("Student-8 Name: " + st8.Item1);
    }
}
```

**Output:**

```cs
Student-1 Name: Mohan
Student-2 Name: Sohan
Student-3 Name: Soniya
Student-4 Name: Rohan
Student-5 Name: Siya
Student-6 Name: Riya
Student-7 Name: Rohit
Student-8 Name: Manita

```