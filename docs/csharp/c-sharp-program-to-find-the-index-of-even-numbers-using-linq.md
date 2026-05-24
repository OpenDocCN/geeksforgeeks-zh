# 使用 LINQ 找到偶数索引的 C# 程序

> 原文:[https://www . geeksforgeeks . org/c-sharp-program-查找偶数索引-使用-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-find-the-index-of-even-numbers-using-linq/)

给定一个数组，现在我们的任务是使用 LINQ 找到给定数组中偶数的索引值。LINQ 被称为语言集成查询，并于 1986 年引入.NET 3.5。它赋予。NET 语言生成查询以从数据源检索数据。所以为了完成这个任务，我们使用了 LINQ 的[选择()](https://www.geeksforgeeks.org/linq-projection-operator-select/)和[的方法。](https://www.geeksforgeeks.org/linq-filtering-operator-where/)

**示例:**

```cs
Input : { 2, 3, 4, 5, 11 }
Output : Index:0 - Number: 2
         Index:2 - Number: 4

Input  : { 2, 3, 4, 5, 6, 23, 31 }
Output : Index:0 - Number: 2
         Index:2 - Number: 4
         Index:4 - Number: 6
```

**进场:**

**1。**创建一个整数类型列表，并向其中添加元素。

**2。**获取列表中出现的数字的索引。

```cs
var indexdata = data.Select((val, indexvalue) => new
                    { 
                        Data = val, 
                        IndexPosition = indexvalue
                    }).Where(n => n.Data % 2 == 0).Select(
                    result => new 
                    { 
                        Number = result.Data,
                        IndexPosition = result.IndexPosition 
                    });
```

**3。**显示索引和数字。

```cs
foreach (var i in indexdata)
{
    Console.WriteLine("Index:" + i.IndexPosition + 
                      " - Number: " + i.Number);
}
```

**示例:**

## C#

```cs
// C# program to find the index value of
// the even numbers using LINQ
using System;
using System.Collections.Generic;
using System.Linq;

class GfG{

static void Main(string[] args)
{

    // Creating a list of integer type
    List<int> data = new List<int>();

    // Add elements to the list
    data.Add(2);
    data.Add(3);
    data.Add(4);
    data.Add(5);
    data.Add(6);
    data.Add(12);
    data.Add(11);

    // Get the index of numbers
    var indexdata = data.Select((val, indexvalue) => new
                    { 
                        Data = val, 
                        IndexPosition = indexvalue
                    }).Where(n => n.Data % 2 == 0).Select(
                    result => new 
                    { 
                        Number = result.Data,
                        IndexPosition = result.IndexPosition 
                    });

    // Display the index and numbers
    // of the even numbers from the array
    foreach(var i in indexdata)
    {
        Console.WriteLine("Index Value:" + i.IndexPosition + 
                          " - Even Number: " + i.Number);
    }
}
}
```

**输出:**

```cs
Index Value:0 - Even Number: 2
Index Value:2 - Even Number: 4
Index Value:4 - Even Number: 6
Index Value:5 - Even Number: 12
```