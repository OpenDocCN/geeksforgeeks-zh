# C# 程序，使用 LINQ

只打印那些数值小于整数数组中所有元素平均值的数字

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-print-only-那些值小于整数数组中所有元素平均值的数字-使用-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-print-only-those-numbers-whose-value-is-less-than-average-of-all-elements-in-an-integer-array-using-linq/)

语言集成查询(LINQ)是 C# 中统一的查询语法，用于从不同的来源检索数据。它消除了编程语言和数据库之间的不匹配，还为不同类型的数据源提供了单一的查询接口。在本文中，我们将学习如何使用 C# 中的 LINQ 只打印那些值小于整数数组中所有元素平均值的数字。

**例:**

```cs
Input: 464, 23, 123, 456, 765, 345, 896, 13, 4
Output: Average is 343
So the numbers less than the average are:
23 123 13 4 

Input: 264, 3, 223, 556, 1, 965, 145, 2, 14
Output: Average is 241
So the numbers less than the average are:
3 223 1 145 2 14
```

**方法:**

> 到只打印那些值小于数组中所有元素平均值的数字我们使用以下方法:
> 
> *   Stores integers (inputs) in an array.
> *   Use the sum () method to calculate the sum of elements.
> *   The average value of the array is calculated by dividing the sum by the length of the array.
> *   By using LINQ query, we will store the number less than the average of the array in the iterator.
> *   Now iterate over the iterator and print the integer.

**例:**

## c#

```cs
// C# program to display only those numbers whose value is
// less than average of all elements in an array using LINQ
using System;
using System.Linq;

class GFG{

static void Main()
{

    // Storing integers in an array
    int[] Arr = { 464, 23, 123, 456, 765, 345, 896, 13, 4 };

    // Find the sum of array
    int total = Arr.Sum();

    // Find the average of array
    int avg = total / Arr.Length;

    // Store the numbers in an iterator
    var nums = from num in Arr where num < avg select num;

    // Display the result
    Console.WriteLine("Average is " + avg);
    Console.WriteLine("The Numbers:");
    foreach(int n in nums)
    {
        Console.Write(n + " ");
    }
    Console.WriteLine();
}
}
```

**输出:**

```cs
Average is 343
The Numbers:
23 123 13 4 
```