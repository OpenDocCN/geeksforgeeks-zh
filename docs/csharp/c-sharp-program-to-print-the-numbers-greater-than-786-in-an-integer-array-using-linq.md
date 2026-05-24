# 使用 LINQ 打印整数数组中大于 786 的数字的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-print-the-numbers-in-a-integer-array-use-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-print-the-numbers-greater-than-786-in-an-integer-array-using-linq/)

语言集成查询(LINQ)是 C# 中统一的查询语法，用于从不同的来源检索数据。它消除了编程语言和数据库之间的不匹配，还为不同类型的数据源提供了单一的查询接口。在本文中，我们将学习如何使用 LINQ 在数组中显示大于 786 的数字。

**例:**

```cs
Input: 1, 234, 456, 678, 789, 987, 654, 345
Output: 789, 987 

Input: 3, 134, 856, 578, 789, 187, 854, 945
Output: 856, 854, 945
```

**方法:**

> 到在整数数组中打印大于 786 的数字我们使用以下方法:
> 
> *   Stores integers (inputs) in an array.
> *   By using LINQ query, we store numbers greater than 786 in iterators.
> *   Now iterate over the iterator and print the integer.

**例:**

## c#

```cs
// C# program to display the numbers greater than 786 in
// an integer array using LINQ
using System;
using System.Linq;

class GFG{

static void Main()
{

    // Input
    int[] Arr = { 1, 234, 456, 678, 789, 987, 654, 345 };

    // From the array the numbers greater than 786 are
    // stored in to the iterator numbers.
    var numbers = from number in Arr where number > 786 select number;

    // Display the output
    Console.WriteLine("The numbers larger than 786 are :");
    foreach(int n in numbers)
    {
        Console.Write(n + " ");
    }
}
}
```

**输出:**

```cs
The numbers larger than 786 are :
789 987 
```