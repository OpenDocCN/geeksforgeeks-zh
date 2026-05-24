# LINQ 聚集功能

> 原文:[https://www.geeksforgeeks.org/aggregation-function-in-linq/](https://www.geeksforgeeks.org/aggregation-function-in-linq/)

在 LINQ，聚合函数是用于从值集合中计算单个值的函数。聚合函数的实际例子是根据全年收集的读数计算 2018 年的年降雨量。另一个例子是，sum 函数用于求给定数组或序列中存在的值的和。

![](img/000f71c70b7f606418937b87c5ea4f21.png)

以下是用于执行聚合操作的方法列表:

| 方法 | 描述 |
| **聚合** | 它对集合的值执行自定义聚合操作。 |
| **[平均值](https://www.geeksforgeeks.org/linq-how-to-find-average-of-the-given-sequence/)** | 它计算一组值的平均值。 |
| **[计数](https://www.geeksforgeeks.org/count-the-number-of-element-present-in-the-sequence-in-linq/)** | 它计算集合中的元素，可选地只计算那些满足谓词函数的元素。 |
| **LongCount** | 它计算大集合中的元素，可选地只计算那些满足谓词函数的元素。 |
| **[Max](https://www.geeksforgeeks.org/linq-how-to-find-maximum-value-of-the-given-sequence/)** | 它确定集合中的最大值。 |
| **[Min](https://www.geeksforgeeks.org/linq-how-to-find-minimum-value-of-the-given-sequence/)** | 它确定集合中的最小值。 |
| **[总和](https://www.geeksforgeeks.org/linq-how-to-find-the-sum-of-the-given-sequence/)** | 它计算集合中值的总和。 |

**例 1:**

```cs
// C# program to illustrate how to
// find the sum of the given sequence
using System;
using System.Linq;

public class GFG {

    // Main Method
    static public void Main()
    {

        int[] sequence = {20, 40, 50, 68, 90, 
                          89, 99, 9, 57, 69};

        Console.WriteLine("The sum of the given sequence is: ");

        // Finding sum of the given sequence
        // Using Sum function
        int result = sequence.Sum();
        Console.WriteLine(result);
    }
}
```

**Output:**

```cs
The sum of the given sequence is: 
591

```