# 使用 LINQ 对学生姓名进行降序排序的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-sort-student-name-in-降序-use-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-sort-student-names-in-descending-order-using-linq/)

给定一个学生姓名列表，现在我们的任务是使用 LINQ 对列表中给出的姓名进行降序排序，这个任务可以使用 LINQ 的 [OrderByDescending()](https://www.geeksforgeeks.org/linq-sorting-operator-orderbydescending/) 方法来完成。此方法用于按降序对集合中的元素进行排序。在 LINQ 查询中使用此方法时，不需要添加额外的条件来按降序对列表进行排序。

**例:**

```cs
Input  : [ "sai", "narendra", "Mohan", "sundar", "vasu" ]
Output : [ "vasu", "sundar", "sai", "narendra", "mohan" ]

Input  : [ "akhil", "amrutha", "yeswanth", "praveen" ]
Output : [ "yeswanth", "praveen", "amrutha", "akhil" ]
```

**接近**

> *   创建并初始化类型字符串的结构名称列表。例如 arr。
> *   使用 OrderByDescending()方法对列表(命名为 arr)进行排序。
> 
> ```cs
> var finalres = arr.OrderByDescending(n => n);
> ```
> 
> *   使用 foreach 循环显示结果。

## c#

```cs
// C# program to sort student names in 
// descending order using Linq.
using System;
using System.Linq;
using System.Collections.Generic;

class GFG{

static void Main(string[] args)
{

    // Creating and initializing list
    List<string> students = new List<string>(){ "akhil", "amrutha", 
                                                "yeswanth", "praveen" };

    // Sorting the student names in descendong order
    var result = students.OrderByDescending(n => n);

    // Display the sorted list
    Console.Write("Sorted list in Descending order:\n");
    foreach (string student in result)
    {
        Console.Write(student + " ");
    }
}
}
```

**输出**

```cs
Sorted list in Descending order:
yeswanth praveen amrutha akhil 
```