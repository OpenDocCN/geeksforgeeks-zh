# 使用 LINQ 并行查询生成随机偶数的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-程序生成-随机-偶数-使用-linq-parallel-query/](https://www.geeksforgeeks.org/c-sharp-program-to-generate-random-even-numbers-using-linq-parallel-query/)

LINQ 被称为语言集成查询，并于 1986 年引入.NET 3.5。它给了。NET 语言生成或创建查询以从数据源检索数据。在本文中，我们将使用 LINQ 并行生成随机偶数。因此，我们将使用 ParallelQuery{TSource}在给定范围内并行生成整数序列。与此同时，我们必须使用 where 和 select 子句来获得偶数。请记住，如果停止值小于 0 或开始+停止-1 大于最大值，它将引发 ArgumentOutOfRangeException。

**语法:**

```cs
IEnumerable<int> variable = ((ParallelQuery<int>)ParallelEnumerable.Range(start,
                            stop)).Where(x => x % 2 == 0).Select(i => i);
```

其中*开始*是序列中的第一个整数值，*停止*是要生成的序列整数的数量。

**例:**

```cs
Input : Range(start, stop) = Range(1, 20)
Output :
2
6
12
16
4
8
14
18
10
20

Input : Range(start, stop) = Range(10, 20)
Output :
10
12
14
16
18
20
22
24
26
28
```

**进场:**

> 要并行打印偶数，请遵循以下步骤:
> 
> 1.  Implement parallel query {TSource} and mention scope.
> 2.  Use where clause to check whether the modulus of y divided by 2 is equal to zero.
> 3.  Now select to check whether the value of the j variable is greater than or equal to the value of the variable (i.e. j).
> 4.  Use foreach loop
> 
> 迭代偶数

**例:**

## c#

```cs
// C# program to generate random even numbers
// using LINQ Parallel Query
using System;
using System.Collections.Generic;
using System.Linq;

class GFG{

static void Main(string[] args)
{

    // Creating data
    IEnumerable<int> data = ((ParallelQuery<int>)ParallelEnumerable.Range(

                            // Condition for generating even numbers
                            10, 20)).Where(i => i % 2 == 0).Select(
                                       value => value);

    // Display even numbers
    foreach(int even in data)
    {
        Console.WriteLine(even);
    }
}
}
```

**输出:**

```cs
12
14
16
18
20
22
24
26
28
10
```