# 使用 LINQ 聚合()方法计算数组元素之和的 C# 程序

> 原文:[https://www . geeksforgeeks . org/c-sharp-使用 linq 聚合方法计算数组元素总和的程序/](https://www.geeksforgeeks.org/c-sharp-program-to-calculate-the-sum-of-array-elements-using-the-linq-aggregate-method/)

给定一个整数数组，现在我们计算数组元素的和。所以我们使用 LINQ 的[聚合()](https://www.geeksforgeeks.org/linq-how-to-find-aggregate-of-the-given-sequence/)方法。此方法将函数应用于源序列的所有元素，并计算累积结果和返回值。该方法以三种不同的方式重载:

*   **aggregate < source, cumulative, tresult > (ienumerable < source, cumulative, function < cumulative, source, cumulative >, function < cumulative, tresult >):** It applies an accumulator function to the specified sequence. Here, the seed value is used to define the starting accumulator value and the function is used to select the final result value.
*   **Aggregate < Tsource, Tcumulative > (ienumerable < Tsource >, Tcumulative, func < Tcumulative, Tsource, Tcumulative >):** It applies an accumulator function to the specified sequence. Here, the specified seed value is used to define the starting accumulator value.
*   **聚合<TSource>(IEnumerable<t source>，Func < TSource，t source，TSource > ):** 它对指定的序列应用累加器功能。

**例:**

```cs
Input: { 34, 27, 34, 5, 6 }
Output: Sum = 106

Input: { 3, 4, 27, 34, 15, 26, 234, 123 }
Output: Sum = 466
```

**进场:**

**1。**创建并初始化整数类型的数组

**2。**现在使用 Aggregate()函数求数组的和。

```cs
sum = arr.Aggregate((element1,element2) => element1 + element2);
```

**3。**显示数组元素的总和

**例:**

## c#

```cs
// C# program to finding the sum of the array elements
// using Aggregate() Method
using System;
using System.Linq;

class GFG{

static void Main(string[] args)
{

    // Creating and initializing the array
    // with integer values
    int[] arr = { 1, 2, 3, 14, 5, 26, 7, 8, 90, 10};
    int sum = 0;

    // Finding the sum of the elements of arr
    // using Aggregate() Method
    sum = arr.Aggregate((element1, element2) => element1 + element2);

    // Displaying the final output
    Console.Write("Sum is : " + sum);
}
}
```

**输出:**

```cs
Sum is : 166
```