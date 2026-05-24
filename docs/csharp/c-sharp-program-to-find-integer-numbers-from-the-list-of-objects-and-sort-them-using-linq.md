# 从对象列表中找到整数并使用 LINQ

对其进行排序的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-find-numbers-from-list-of-objects-and-sort-use-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-find-integer-numbers-from-the-list-of-objects-and-sort-them-using-linq/)

给定一个对象列表，我们需要从对象列表中找到整数倍的数字，并使用 LINQ 对它们进行排序。所以这个任务可以用 OfType()方法完成，然后用 OrderBy()方法完成数字的排序。让我们逐一讨论它们及其语法:

**1。OfType()方法:**用于根据指定的类型过滤 IEnumerable 的元素。如果给定的源为空，则此方法将引发 ArgumentNullException。

**语法:**

> 公共静态系统。类型<tresult>的集合.泛型. IEnumerable <tresult>(本系统。Collections.IEnumerable 源代码)；</tresult></tresult>

**2。** [**OrderBy()方法**](https://www.geeksforgeeks.org/linq-sorting-operator-orderby/) **:** 该方法用于对集合中的元素进行升序排序。如果给定的源为空，则此方法也会引发 ArgumentNullException。

**语法:**

> 公共静态系统。linq . IOrderedEnumerable<tsource>order by < t source，TKey(</tsource>
> 
> 这个系统。集合.泛型. IEnumerable <tsource>列表，函数<tsource>选择器)；</tsource></tsource>

**示例:**

```cs
Input  : ["sai", 100, "mohan", 18, 50, 200, "rajesh", 34]
Output : [18, 34, 50, 100, 200]

Input  : ["raju", 345, 18.0 , "mohan", 189, 193, 30, 200, "rajesh"]
Output : [30, 189, 193, 200, 345]
```

**进场:**

> *   Create an object list using ArrrayList.
> *   Now, using the type < int > () method and the OrderBy () method, we will select integer values from the list and sort the integers, and then use the ToList () method to convert them into the list.
> 
> ```cs
> List<int> result = objList.OfType<int>().OrderBy(num=>num).ToList();
> ```
> 
> *   Use foreach loop to print the list.
> 
> ```cs
> foreach (int integer in result)
>  {
>    Console.Write(integer + " ");
>  }
> ```

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

**Output**

```cs
The Sorted integers are : 
34 50 100 200 
```