# C# |如何获取元组的第七个元素？

> 原文:[https://www . geeksforgeeks . org/c-sharp-如何获取元组中的第七个元素/](https://www.geeksforgeeks.org/c-sharp-how-to-get-seventh-element-of-the-tuple/)

**[Tuple](https://www.geeksforgeeks.org/c-sharp-tuple/)** 是一种数据结构，它为您提供了最简单的方法来表示具有多个值的数据集，这些值可能彼此相关，也可能彼此不相关。 **Item7 属性**用于获取给定元组的第七个元素。它不适用于 1 元组、2 元组、3 元组、4 元组、5 元组和 6 元组，但适用于所有其他剩余元组。

**语法:**

```cs
public T7 Item7 { get; }
```

这里， *T7* 是当前 Tuple < >对象的第七个分量的值。这个元组< >可以是 7 元组，也可以是 8 元组。

**示例:**在下面的代码中，您可以看到我们正在访问每个元组的第七个元素。

```cs
// C# program to illustrate how to get 
// the seventh element of the tuple
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Taking 7-tuple
        var st7 = Tuple.Create("Rohit", 21, "IT", 2017, 
                        "21-Apr-1994", 384749829, 1);

        Console.WriteLine("Student-7 Position.: " + st7.Item7);

        // Taking 8-tuple
        var st8 = Tuple.Create("Manita", 24, "CSE", 2013, 
                   "03-Aug-1991", 235678909, 2, "C#");

        Console.WriteLine("Student-8 Position: " + st8.Item7);
    }
}
```

**输出:**

```cs
Student-7 Position.: 1
Student-8 Position: 2

```