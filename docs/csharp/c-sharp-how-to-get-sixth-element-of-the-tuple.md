# C# |如何获取元组的第六元素？

> 原文:[https://www . geeksforgeeks . org/c-sharp-如何获取元组中的第六个元素/](https://www.geeksforgeeks.org/c-sharp-how-to-get-sixth-element-of-the-tuple/)

**[Tuple](https://www.geeksforgeeks.org/c-sharp-tuple/)** 是一种数据结构，它为您提供了最简单的方法来表示具有多个值的数据集，这些值可能彼此相关，也可能彼此不相关。 **Item6 属性**用于获取给定元组的第六个元素。它不适用于 1 元组、2 元组、3 元组、4 元组和 5 元组，但适用于所有其他剩余元组。

**语法:**

```cs
public T6 Item6 { get; }
```

这里， *T6* 是当前 Tuple < >对象的第六个分量的值。这个元组< >可以是 6 元组，或者 7 元组，或者 8 元组。

**示例:**在下面的代码中，您可以看到我们正在访问每个元组的第六个元素。

```cs
// C# program to illustrate how to get 
// the sixth element of the tuple
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Taking 6-tuple
        var st6 = Tuple.Create("Riya", 24, "ME", 2015,
                               "30-May-1991", 230134832);

        Console.WriteLine("Student-6 Contact No.: " + st6.Item6);

        // Taking 7-tuple
        var st7 = Tuple.Create("Rohit", 21, "IT", 2017, 
                        "21-Apr-1994", 384749829, 20000);

        Console.WriteLine("Student-7 Contact No.: " + st7.Item6);

        // Taking 8-tuple
        var st8 = Tuple.Create("Manita", 24, "CSE", 2013, 
                   "03-Aug-1991", 235678909, 34000, "C#");

        Console.WriteLine("Student-8 Contact No.: " + st8.Item6);
    }
}
```

**输出:**

```cs
Student-6 Contact No.: 230134832
Student-7 Contact No.: 384749829
Student-8 Contact No.: 235678909

```