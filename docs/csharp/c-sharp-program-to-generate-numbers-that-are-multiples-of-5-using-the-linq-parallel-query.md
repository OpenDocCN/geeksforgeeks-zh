# 使用 LINQ 并行查询生成 5 的倍数的 C# 程序

> 原文:[https://www . geeksforgeeks . org/c-sharp-使用-linq-parallel-query 程序生成 5 的倍数的数字/](https://www.geeksforgeeks.org/c-sharp-program-to-generate-numbers-that-are-multiples-of-5-using-the-linq-parallel-query/)

[LINQ](https://www.geeksforgeeks.org/linq-language-integrated-query/) 被称为语言集成查询，它是在。NET 3.5。它赋予了。NET 语言生成查询以从数据源检索数据。它消除了编程语言和数据库之间的不匹配，并且无论使用哪种类型的数据源，用于创建查询的语法都是相同的。在本文中，我们将从给定的范围并行生成 5 的倍数。因此，为了完成我们的任务，我们使用内置的并行查询类来并行生成数字。

**语法:**

> ((parallel query<int>)parallel numerable。范围(开始、停止)

其中 start 是起始数，stop 是结束数。

**示例:**

```cs
Input  : Range(3, 20)
Output :
10
15
20
5

Input  : Range(1,10)
Output :
5
10
```

**示例:**

在下面的示例中，首先，我们将创建一个范围从 3 到 20 的 IEnumerable 类型的数字集合，然后使用 Where(n => n% 5 == 0)函数生成给定范围之间的 5 的倍数。生成 5 的倍数后，我们将在输出屏幕上显示这些数字。

## C#

```cs
// C# program to generate numbers that 
// are multiples of 5 
using System;
using System.Collections.Generic;
using System.Linq;

class GFG{

static void Main(string[] args)
{

    // Input numbers from 3 to 20
    // Using ParallelQuery
    IEnumerable<int> result = ((ParallelQuery<int>)ParallelEnumerable.Range(3, 20))

    // Generate numbers that are multiples 
    // of 5 in parallel
    .Where(n => n % 5 == 0).Select(res => res);

    // Display the numbers which are multiples of 5
    Console.WriteLine("Numbers are:");
    foreach (int numbers in result) 
    {
        Console.WriteLine(numbers); 
    }
}
}
```

**输出:**

```cs
Numbers are:
10
15
20
5
```