# 使用 LINQ 排序法对字符串名称列表进行排序的 C# 程序

> 原文:[https://www . geeksforgeeks . org/c-sharp-program-to-sort-list-string-name-使用-linq-orderby-method/](https://www.geeksforgeeks.org/c-sharp-program-to-sort-a-list-of-string-names-using-the-linq-orderby-method/)

给定一个字符串名称列表，现在我们的任务是使用 LINQ 的 [OrderBy()](https://www.geeksforgeeks.org/linq-sorting-operator-orderby/) 方法对列表中给出的名称进行排序。此方法用于按升序对集合中的元素进行排序。在 LINQ 查询中使用此方法时，不需要添加额外的条件来按升序对列表进行排序。

**例:**

```cs
Input    : [ "Raj", "Amisha", "Mohan", "Mohit", "Bhuvan" ]
Output : [ "Amisha", "Bhuvan", "Mohan", "Mohit", "Raj" ]

Input   : [ "Amu", "Amisha", "Sumita", "Gita" ]
Output : [ "Amisha", "Amu", "Gita", "Sumita" ]
```

**进场:**

**1。**创建并初始化字符串类型列表。例如 arr。

**2。**使用 OrderBy()方法对列表(命名为 arr)进行排序。

```cs
var finalres = arr.OrderBy(n => n);
```

**3。**使用 foreach 循环显示结果。

**例:**

## c#

```cs
// C# program to sort a list of string type
// Using OrderBy() method
using System;
using System.Linq;
using System.Collections.Generic;

class GFG{

static void Main(string[] args)
{

    // Creating and initializing list of string type
    List<string> arr = new List<string>(){ "Raju", "Avinash", 
                                           "Sandeep", "Vineeth",
                                           "Naveen" };

    // Using order by method we sort the list
    var finalres = arr.OrderBy(n => n);

    // Display the list
    Console.WriteLine("Sorted names are:");
    foreach (string data in finalres)
    {
        Console.Write(data + " ");
    }
}
}
```

**输出:**

```cs
Sorted names are:
Avinash Naveen Raju Sandeep Vineeth 
```