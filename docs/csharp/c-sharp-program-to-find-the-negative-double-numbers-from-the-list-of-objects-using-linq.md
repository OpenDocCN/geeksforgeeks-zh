# 使用 LINQ 从对象列表中找到双负数的 C# 程序

> 原文:[https://www . geeksforgeeks . org/c-sharp-program-to-find-the-negative-double-numbers-from-list-of-objects-use-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-find-the-negative-double-numbers-from-the-list-of-objects-using-linq/)

给定一个对象列表，我们需要从对象列表中找到负双精度值，这个任务可以使用 OfType()方法和 [Where()](https://www.geeksforgeeks.org/linq-filtering-operator-where/) 方法来完成。 [OfType()](https://www.geeksforgeeks.org/linq-filtering-operator-oftype/) 方法用于根据指定的类型过滤 IEnumerable 的元素。或者换句话说，此方法用于根据列表或序列源将集合中的项转换为指定类型的能力来筛选列表或序列源。如果给定的源为空，它将引发 ArgumentNullException。

**语法:**

> 公共静态系统。类型<tresult>的集合.泛型. IEnumerable <tresult>(本系统。Collections.IEnumerable 源代码)；</tresult></tresult>

[其中()](https://www.geeksforgeeks.org/linq-filtering-operator-where/)方法用于根据谓词函数过滤值。或者我们可以说，它根据给定的条件或标准从给定的序列或列表中返回值。

**语法:**

> 其中 <tsource>(IEnumerable <tsource>，Func <tsource>)</tsource></tsource></tsource>

**示例:**

```cs
Input  : ["sai", 100, "mohan", -18.0, -30.2, 200, "rajesh"]
Output : [-18.0, -32.2]

Input  : ["raju", -345.0, 18.3 , "mohan", -18.0, 193, -30.2, 200, "rajesh"]
Output : [-345.0, -18.0, -32.2]
```

**进场:**

> *   Create an object list.
> 
> ```cs
> List<object> objList = new List<object>()
> ```
> 
> *   Now use the type () method and the Where () method to select a double value less than zero, that is, a negative double value.
> 
> ```cs
> List<double> result = objList.OfType<double>().Where(n => n < 0).ToList();
> ```
> 
> *   Use foreach loop to print double negative numbers.
> 
> ```cs
> foreach (double negative in result)
> {
>     Console.Write(negative + "  ");
> } 
> ```

## C#

```cs
// C# program to find the negative double
// numbers from the given list of objects
using System;
using System.Linq;
using System.Collections.Generic;

class GFG{

static void Main(string[] args)
{

    // Creating and initialize the list of object
    List<object> objList = new List<object>(){
    "raju", -345.0, 18.3 , "mohan", -18.0,
    193, -30.2, 200, "rajesh" };

    // Filtering the negative double objects
    // from objList and convert to list
    List<double> result = objList.OfType<double>().Where(n => n < 0).ToList();

    // Display the output list
    Console.Write("Negative numbers are:");
    foreach (double negative in result)
    {
        Console.Write(negative + "  ");
    }
}
}
```

**输出:**

```cs
Negative numbers are:-345  -18  -30.2  
```