# 用 `OrderBy()` 方法演示 LINQ `Intersect()` 方法示例的 C# 程序

> 原文：[https://www.geeksforgeeks.org/c-sharp-program-to-demonstrate-the-example-of-linq-intersect-method-with-orderby-method/](https://www.geeksforgeeks.org/c-sharp-program-to-demonstrate-the-example-of-linq-intersect-method-with-orderby-method/)

LINQ 被称为语言集成查询，它是在 .NET 3.5 中引入的。它提供了 .NET 语言创建查询以从数据源检索数据的能力。在本文中，我们将使用 `OrderBy()` 方法演示 `Intersect()` 方法的示例。

## `Intersect()` 方法
这是用来从两个给定的列表中获取公共元素。或者我们可以说这个方法返回两个列表的交集。它在 `Queryable` 类和 `Enumerable` 类中都可用。

**语法**:
```csharp
data1.Intersect(data2)
```
其中 `data1` 是第一个列表，`data2` 是第二个列表。

## `OrderBy()` 方法
该方法的唯一目的是按升序对给定的元素列表进行排序。使用此方法编写 LINQ 查询时，不需要编写额外的条件来按升序对数组进行排序。

**语法**:
```csharp
data1.OrderBy(i => i)
```
其中 `i` 是迭代器。

现在，我们将 `Intersect()` 和 `OrderBy()` 方法结合起来，首先使用 `Intersect()` 函数获取公共元素，然后从结果中使用 `OrderBy()` 函数以升序获取数据，并使用迭代器显示数据。为此，我们使用以下查询：
```csharp
data1.Intersect(data2).OrderBy(i => i);
```
其中 `data1` 是第一个列表，`data2` 是第二个列表。

**例**:
```csharp
Input: { 10, 20, 30, 40, 50, 60, 70 }
       { 50, 60, 70, 80, 90, 100 }
Output: 50 60 70

Input: { 10, 20, 30 }
       { 50, 60, 70 }
Output:
No Output
```

**步骤**:
1.  创建并初始化两个名为 `data1` 和 `data2` 的 `List<int>` 类型列表。
2.  现在我们使用下面的查询从这些列表中找到公共元素，然后按升序排序。
    ```csharp
    final = data1.Intersect(data2).OrderBy(i => i);
    ```
3.  使用 `foreach` 循环迭代结果。
    ```csharp
    foreach (var j in final)
    {
        Console.WriteLine(j + " ");
    }
    ```

**示例**:
```csharp
// C# program to illustrate how to use Intersect() method
// with OrderBy() method in LINQ
using System;
using System.Linq;
using System.Collections.Generic;

class GFG{

static void Main(string[] args)
{

// Create first list
    List<int> data1 = new List<int>(){
        10, 20, 30, 40, 50, 60, 70 };

// Create second list
    List<int> data2 = new List<int>() {
        50, 60, 70, 80, 90, 100 };

// Finding the intersection of two lists and
    // then order them in ascending order.
    var final = data1.Intersect(data2).OrderBy(i => i);

// Display the numbers
    Console.WriteLine("Final Result is: ");
    foreach(var j in final)
    {
        Console.WriteLine(j + " ");
    }
}
}
```

**输出**:
```csharp
Final Result is: 
50 60 70 
```