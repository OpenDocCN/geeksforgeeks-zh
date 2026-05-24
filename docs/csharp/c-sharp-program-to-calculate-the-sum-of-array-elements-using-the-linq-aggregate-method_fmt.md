# 使用 LINQ Aggregate() 方法计算数组元素之和的 C# 程序

> 原文：[https://www.geeksforgeeks.org/c-sharp-program-to-calculate-the-sum-of-array-elements-using-the-linq-aggregate-method/](https://www.geeksforgeeks.org/c-sharp-program-to-calculate-the-sum-of-array-elements-using-the-linq-aggregate-method/)

给定一个整数数组，现在我们计算数组元素的和。所以我们使用 LINQ 的 `Aggregate()` 方法。此方法将函数应用于源序列的所有元素，并计算累积结果和返回值。该方法以三种不同的方式重载：

*   `Aggregate<TSource, TAccumulate>(IEnumerable<TSource>, TAccumulate, Func<TAccumulate, TSource, TAccumulate>)`：它对指定的序列应用累加器函数。这里，种子值用于定义起始累加器值，函数用于选择最终结果值。
*   `Aggregate<TSource, TAccumulate>(IEnumerable<TSource>, TAccumulate, Func<TAccumulate, TSource, TAccumulate>)`：它对指定的序列应用累加器函数。这里，指定的种子值用于定义起始累加器值。
*   `Aggregate<TSource>(IEnumerable<TSource>, Func<TSource, TSource, TSource>)`：它对指定的序列应用累加器功能。

## 示例

```cs
Input: { 34, 27, 34, 5, 6 }
Output: Sum = 106

Input: { 3, 4, 27, 34, 15, 26, 234, 123 }
Output: Sum = 466
```

## 实现步骤

1.  创建并初始化整数类型的数组。
2.  现在使用 `Aggregate()` 函数求数组的和。
    ```cs
    sum = arr.Aggregate((element1,element2) => element1 + element2);
    ```
3.  显示数组元素的总和。

## C# 示例代码

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

## 输出

```cs
Sum is : 166
```