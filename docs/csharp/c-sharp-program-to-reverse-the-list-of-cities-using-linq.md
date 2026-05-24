# 使用 LINQ 逆转城市名单的 C# 程序

> 原文:[https://www . geeksforgeeks . org/c-sharp-program-to-reverse-list-city-use-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-reverse-the-list-of-cities-using-linq/)

给定一个城市名称列表，我们需要反转城市列表，这可以使用 LINQ 的 reverse()方法来完成。 [Reverse()](https://www.geeksforgeeks.org/linq-sorting-operator-reverse/) 方法反转指定列表中元素的顺序。它在可查询类和可枚举类中都可用。如果给定的源为空，它将返回 ArgumentNullException。

**语法:**

```cs
public static void Reverse ();
```

**例:**

```cs
Input  : ["mumbai", "pune", "bangalore", "hyderabad"]
Output : ["hyderabad", "bangalore", "pune", "mumbai"] 

Input  : ["chennai", "vizag", "delhi"]
Output : ["delhi", "vizag", "chennai"]
```

**方法:**

> *   使用数组列表定义城市列表。
> *   使用 reverse()方法反转城市列表。
> 
> ```cs
> cities.Reverse();
> ```
> 
> *   最后，使用 foreach 循环打印结果数组。
> 
> ```cs
> foreach (var city in cities)
> {
>     Console.Write(city + " ");
> }
> ```

## c#

```cs
using System;
using System.Linq;
using System.Collections.Generic;

class geek
{
    static void Main(string[] args)
    {
        List<string> cities = new List<string>() {"mumbai","hyderabad","pune","bangalore"};
        // reversing the cities arrayList
        cities.Reverse();

        Console.Write("The Reversed list = ");
        Console.Write("[ ");
        foreach (var city in cities)
        {
            Console.Write(city + " ");
        }
        Console.Write(" ]");
    }
}
```

**输出**

```cs
The Reversed list = [ bangalore pune hyderabad mumbai  ]
```