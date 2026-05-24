# C# |如何获取元组的第二个元素？

> 原文:[https://www . geeksforgeeks . org/c-sharp-如何获取元组中的第二个元素/](https://www.geeksforgeeks.org/c-sharp-how-to-get-second-element-of-the-tuple/)

**[Tuple](https://www.geeksforgeeks.org/c-sharp-tuple/)** 是一种数据结构，它为您提供了最简单的方法来表示具有多个值的数据集，这些值可能彼此相关，也可能彼此不相关。 **Item2 属性**用于获取给定元组的第二个元素。它不适用于 1 元组，也不适用于所有其他剩余元组。

**语法:**

```cs
public T2 Item2 { get; }
```

这里， *T2* 是当前 Tuple < >对象的第二个分量的值。这个元组< >可以是 2 元组，或 3 元组，或 4 元组，或 5 元组，或 6 元组，或 7 元组，或 8 元组。

**示例:**在下面的代码中，可以看到我们正在访问每个元组的第二个元素。

```cs
// C# program to illustrate how to get 
// the second element of the tuple
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Taking 2-tuple
        var st2 = Tuple.Create("Sohan", 20);
        Console.WriteLine("Student-2 Age: " + st2.Item2);

        // Taking 3-tuple
        var st3 = Tuple.Create("Soniya", 30, "CSE");
        Console.WriteLine("Student-3 Age: " + st3.Item2);

        // Taking 4-tuple
        var st4 = Tuple.Create("Rohan", 29, "CSE", 2015);
        Console.WriteLine("Student-4 Age: " + st4.Item2);

        // Taking 5-tuple
        var st5 = Tuple.Create("Siya", 22, "CSE", 2017,
                                           "20-Mar-1993");

        Console.WriteLine("Student-5 Age: " + st5.Item2);

        // Taking 6-tuple
        var st6 = Tuple.Create("Riya", 24, "CSE", 2015,
                               "30-May-2015", 230134832);

        Console.WriteLine("Student-6 Age: " + st6.Item2);

        // Taking 7-tuple
        var st7 = Tuple.Create("Rohit", 21, "CSE", 2017, 
                        "21-Apr-1998", 384749829, 20000);

        Console.WriteLine("Student-7 Age: " + st7.Item2);

        // Taking 8-tuple
        var st8 = Tuple.Create("Manita", 24, "CSE", 2016, 
                   "03-Aug-1991", 235678909, 34000, "C#");

        Console.WriteLine("Student-8 Age: " + st8.Item2);
    }
}
```

**Output:**

```cs
Student-2 Age: 20
Student-3 Age: 30
Student-4 Age: 29
Student-5 Age: 22
Student-6 Age: 24
Student-7 Age: 21
Student-8 Age: 24

```