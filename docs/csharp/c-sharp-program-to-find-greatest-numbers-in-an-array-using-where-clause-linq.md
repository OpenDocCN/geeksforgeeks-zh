# 使用 WHERE 子句 LINQ 寻找数组中最大数的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-程序查找数组中最大数-使用 where 子句-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-find-greatest-numbers-in-an-array-using-where-clause-linq/)

LINQ 被称为语言集成查询，它是在年引入的。NET 3.5。它赋予*能力。NET* 语言生成查询，从数据源中检索数据。它消除了编程语言和数据库之间的不匹配，并且无论使用哪种类型的数据源，用于创建查询的语法都是相同的。在本文中，我们将学习如何使用 WHERE 子句 LINQ 找到数组中最大的数字。在这里，我们将得到给定数组中大于特定数字的数字。

**例:**

```cs
Input: Array of Integers: 100,200,300,450,324,56,77,890
Value: 500
Output: Numbers greater than 500 are: 890

Input: Array of Integers: 34,56,78,100,200,300,450,324,56,77,890
Value: 100
Output: Numbers greater than 100 are: 200,300,450,324,890
```

**方法:**

> 要使用 WHERE 子句显示数组中最大的数字，LINQ 遵循以下方法:
> 
> 1.  Stores integers (inputs) in an array.
> 2.  Use the for loop to calculate the sum of elements.
> 3.  Use the where function to check numbers greater than a specific value.
> 4.  By using LINQ query, we store numbers in iterators.
> 5.  Now iterate over the iterator and print the integer.

**例:**

## c#

```cs
// C# program to print the greatest numbers in an array
// using WHERE Clause LINQ
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

class GFG{

static void Main()
{

    // Array of numbers
    int[] array1 = { 34, 56, 78, 100, 200, 300,
                     450, 324, 56, 77, 890 };

    // Now get the numbers greater than 100 and 
    // store in big variable using where clause
    var big = from value in array1 where value > 100 select value;
    Console.WriteLine("Numbers that are greater than 100 are  :");

    // Get the greater numbers
    foreach (var s in big)
    {
        Console.Write(s.ToString() + " ");
    }
    Console.Read();
}
}
```

**输出:**

```cs
Numbers that are greater than 100 are  :
200 300 450 324 890 
```