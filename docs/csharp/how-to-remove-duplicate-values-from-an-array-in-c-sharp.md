# 如何在 C# 中删除数组中的重复值？

> 原文:[https://www . geeksforgeeks . org/如何从 c-sharp 数组中删除重复值/](https://www.geeksforgeeks.org/how-to-remove-duplicate-values-from-an-array-in-c-sharp/)

数组是一组由公共名称引用的同构元素，可以包含重复的值。在 C# 中，我们不能从指定的数组中移除元素，但是我们可以创建一个包含不同元素的新数组。为此，我们使用 [Distinct()](https://www.geeksforgeeks.org/linq-set-operator-distinct/) 函数。该函数给出了给定序列的不同值。如果给定数组为空，此方法将引发 ArgumentNullException。

**语法**:

```cs
array_name.Distinct()
```

其中 array_name 是一个输入数组。

**示例:**

```cs
Input : data = { 10, 20, 230, 34, 56, 10, 12, 34, 56, 56 }
Output :
10
20
230
34
56
12
Input : data = { "java", "java", "c", "python", "cpp", "c" }
Output :
java
c
python
cpp
```

**接近**

**1。**用任何类型的元素创建一个数组，如 int、string、float 等。

**2。**应用不同的函数并转换为数组

```cs
data.Distinct().ToArray();
```

**3。**这里，ToArray()方法转换数组中的值。

**4。**通过遍历数组来显示唯一的元素

```cs
Array.ForEach(unique, i => Console.WriteLine(i));
```

**例 1:**

## C#

```cs
// C# program to remove duplicate elements from the array
using System;
using System.Linq;

class GFG{

public static void Main()
{

    // Declare an array of integer type
    int[] data = { 10, 20, 230, 34, 56, 10, 12, 34, 56, 56 };
    Console.WriteLine("Array before removing duplicate values: ");
    Array.ForEach(data, i => Console.WriteLine(i));

    // Use distinct() function
    // To create an array that contain distinct values
    int[] unique = data.Distinct().ToArray();

    // Display the final result
    Console.WriteLine("Array after removing duplicate values: ");
    Array.ForEach(unique, j => Console.WriteLine(j));
}
}
```

**输出:**

```cs
Array before removing duplicate values:
10
20
230
34
56
10
12
34
56
56
Array after removing duplicate values:
10
20
230
34
56
12
```

**例 2:**

## C#

```cs
// C# program to remove duplicate elements from the array
using System;
using System.Linq;

class GFG{

public static void Main()
{

    // Declare an array of string type
    string[] data1 = { "Java", "Java", "C", "Python", "CPP", "C" };
    Console.WriteLine("Array before removing duplicate values: ");
    Array.ForEach(data1, i => Console.WriteLine(i));

    // Use distinct() function
    // To create an array that contain distinct values
    string[] unique = data1.Distinct().ToArray();

    // Display the final result
    Console.WriteLine("Array after removing duplicate values: ");
    Array.ForEach(unique, j => Console.WriteLine(j));
}
}
```

**输出:**

```cs
Array before removing duplicate values: 
Java
Java
C
Python
CPP
C
Array after removing duplicate values: 
Java
C
Python
CPP
```