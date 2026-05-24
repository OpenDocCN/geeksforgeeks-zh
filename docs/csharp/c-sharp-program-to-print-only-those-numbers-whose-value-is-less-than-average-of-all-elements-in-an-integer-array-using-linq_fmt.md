# C# 程序，使用 LINQ

只打印那些数值小于整数数组中所有元素平均值的数字

> 原文: [https://www.geeksforgeeks.org/c-sharp-program-to-print-only-those-numbers-whose-value-is-less-than-average-of-all-elements-in-an-integer-array-using-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-print-only-those-numbers-whose-value-is-less-than-average-of-all-elements-in-an-integer-array-using-linq/)

语言集成查询(LINQ)是 C# 中统一的查询语法，用于从不同的来源检索数据。它消除了编程语言和数据库之间的不匹配，还为不同类型的数据源提供了单一的查询接口。在本文中，我们将学习如何使用 C# 中的 LINQ 只打印那些值小于整数数组中所有元素平均值的数字。

## 示例

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

## 方法

要只打印那些值小于数组中所有元素平均值的数字，我们使用以下方法：

*   将整数（输入）存储在数组中。
*   使用 `Sum()` 方法计算元素的总和。
*   数组的平均值通过总和除以数组的 `Length` 来计算。
*   通过使用 LINQ 查询，我们将小于数组平均值的数字存储在迭代器中。
*   现在遍历迭代器并打印整数。

## 代码示例

### C\#

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

### 输出

```cs
Average is 343
The Numbers:
23 123 13 4 
```