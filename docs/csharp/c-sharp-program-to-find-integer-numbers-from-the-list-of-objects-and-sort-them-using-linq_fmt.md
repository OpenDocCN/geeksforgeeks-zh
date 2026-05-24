# 从对象列表中找到整数并使用 LINQ 对其进行排序的 C# 程序

> 原文: [https://www.geeksforgeeks.org/c-sharp-program-to-find-integer-numbers-from-the-list-of-objects-and-sort-them-using-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-find-integer-numbers-from-the-list-of-objects-and-sort-them-using-linq/)

给定一个对象列表，我们需要从对象列表中找到整数倍的数字，并使用 LINQ 对它们进行排序。所以这个任务可以用 `OfType()` 方法完成，然后用 `OrderBy()` 方法完成数字的排序。让我们逐一讨论它们及其语法:

### 1. `OfType()` 方法
用于根据指定的类型过滤 `IEnumerable` 的元素。如果给定的源为空，则此方法将引发 `ArgumentNullException`。

**语法:**
```cs
public static System.Collections.Generic.IEnumerable<TResult> OfType<TResult>(this System.Collections.IEnumerable source);
```

### 2. `OrderBy()` 方法
该方法用于对集合中的元素进行升序排序。如果给定的源为空，则此方法也会引发 `ArgumentNullException`。

**语法:**
```cs
public static System.Linq.IOrderedEnumerable<TSource> OrderBy<TSource, TKey>(this System.Collections.Generic.IEnumerable<TSource> list, Func<TSource, TKey> selector);
```

### 示例
```cs
Input  : ["sai", 100, "mohan", 18, 50, 200, "rajesh", 34]
Output : [18, 34, 50, 100, 200]

Input  : ["raju", 345, 18.0 , "mohan", 189, 193, 30, 200, "rajesh"]
Output : [30, 189, 193, 200, 345]
```

### 进场
*   使用 `ArrayList` 创建一个对象列表。
*   现在，使用 `OfType<int>()` 方法和 `OrderBy()` 方法，我们将从列表中选择整数值并对整数进行排序，然后使用 `ToList()` 方法将它们转换为列表。
```cs
List<int> result = objList.OfType<int>().OrderBy(num=>num).ToList();
```
*   使用 `foreach` 循环打印列表。
```cs
foreach (int integer in result)
{
    Console.Write(integer + " ");
}
```

## C#
```cs
// C# program to find the integer numbers from 
// the list of objects and sort them.
using System;
using System.Linq;
using System.Collections.Generic;

class GFG{

    static void Main(string[] args)
    {

        // Declaring and initializing an arrayList
        // of objects
        List<object> objList = new List<object>(){ 
            "sai", 100, "mohan", 18.0, 50, 200, "rajesh", 34 };

        // Selecting the integers form the list and sorting
        // them using orderby()
        List<int> result = objList.OfType<int>().OrderBy(num => num).ToList();

        // Printing sorted list
        Console.WriteLine("The Sorted integers are : ");
        foreach (int integer in result)
        {
            Console.Write(integer + " ");
        }
    }
}
```

### 输出
```cs
The Sorted integers are : 
34 50 100 200 
```