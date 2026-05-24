# 使用 LINQ 并行生成奇数的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-generate-奇数-in-parallel-use-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-generate-odd-numbers-in-parallel-using-linq/)

LINQ 被称为语言集成查询，它是在年引入的。NET 3.5。它赋予了。NET 语言生成查询以从数据源检索数据。它消除了编程语言和数据库之间的不匹配，并且无论使用哪种类型的数据源，用于创建查询的语法都是相同的。在本文中，我们将使用 LINQ 并行生成奇数。因此，我们将使用 ParallelQuery{TSource}并行生成奇数。与此同时，我们必须使用 where 和 select 子句来获取奇数

**语法:**

```cs
IEnumerable<int> variable = ((ParallelQuery<int>)ParallelEnumerable.Range(start, 
                             stop)).Where(x => x % 2 != 0).Select(i => i);
```

**例:**

```cs
Input: Range(start, stop)= Range(10,11)
Output:
13
17
19
11
15

Input: Range(start, stop)= Range(5,8)
Output:
11
5
7
9
```

**方法:**要并行打印奇数，请遵循以下步骤:

1.  Implement the parallel query {TSource} and mention the range (i.e. 10 to 11).
2.  Use where clause to check that the modulus of y divided by 2 is not equal to zero.
3.  Now select to check whether the value of the j variable is greater than or equal to the value of the variable (i.e. j).
4.  Use foreach loop

迭代奇数

**例:**

## c#

```cs
// C# program to print odd numbers in parallel 
// Using LINQ
using System;
using System.Linq;
using System.Collections.Generic;

class GFG{

static void Main(string[] args)
{

    // Implement parallel Query in the range 10 to 11
    IEnumerable<int> odd = ((ParallelQuery<int>)ParallelEnumerable.Range(10, 11))

    // condition to check for the odd numbers
    .Where(y => y % 2 != 0)

    // Select that odd numbers
    .Select(j => j);

    // Display the odd numbers
    foreach (int n in odd) 
    { 
        Console.WriteLine(n);
    }
    Console.ReadLine();
}
}
```

**输出:**

```cs
13
17
19
11
15
```