# 使用 LINQ OrderBy() 方法对整数列表进行排序的 C# 程序

> 原文：[https://www.geeksforgeeks.org/c-sharp-program-to-sort-a-list-of-integers-using-the-linq-orderby-method/](https://www.geeksforgeeks.org/c-sharp-program-to-sort-a-list-of-integers-using-the-linq-orderby-method/)

给定一个整数列表，现在我们的任务是对给定的整数列表进行排序。所以我们用 LINQ 的 [`OrderBy()`](https://www.geeksforgeeks.org/linq-sorting-operator-orderby/) 方法。此方法用于按升序对集合中的元素进行排序。该方法以两种不同的方式重载：

*   `OrderBy<TSource, TKey>(IEnumerable<TSource>, Func<TSource, TKey>)`：用于根据关键字对给定序列的项进行升序排序，并对给定序列或列表进行稳定排序。
*   `OrderBy<TSource, TKey>(IEnumerable<TSource>, Func<TSource, TKey>, IComparer<TKey>)`：用于通过给定的比较器对给定序列的项进行升序排序。

**例：**

```
Input  : [90, 87, 34, 23, 22, 56, 21, 89]
Output : [21, 22, 23, 34, 56, 87, 89, 90]

Input  : [10, 11, 2, 3, 18, 5,]
Output : [2, 3, 5, 10, 11, 18]
```

## 进场

1.  创建并初始化整数类型列表。例如 `nums`。
2.  使用 `OrderBy()` 方法对列表（命名为 `nums`）进行排序。
    ```cs
    var result_set = nums.OrderBy(num => num);
    ```
3.  使用 `foreach` 循环显示结果。

## C# 示例

```cs
// C# program to sort a list of integers
// Using OrderBy() method
using System;
using System.Linq;
using System.Collections.Generic;

class GFG{

    static void Main(string[] args)
    {
        // Creating and initializing list of integers
        List<int> nums = new List<int>() { 50, 20, 40, 60, 33, 70 };

        // Using OrderBy method we sort the list
        var result_set = nums.OrderBy(num => num);

        // Display the list
        Console.WriteLine("Sorted in Ascending order:");
        foreach (int value in result_set)
        {
            Console.Write(value + " ");
        }
    }
}
```

**输出**

```
Sorted in Ascending order:
20 33 40 50 60 70
```