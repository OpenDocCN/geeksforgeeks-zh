# 如何在 C# 中组合两个没有重复值的数组？

> 原文:[https://www . geeksforgeeks . org/如何在 c-sharp 中组合两个无重复值的数组/](https://www.geeksforgeeks.org/how-to-combine-two-arrays-without-duplicate-values-in-c-sharp/)

给定两个[数组](https://www.geeksforgeeks.org/c-sharp-arrays/)，现在我们的任务是将这些数组合并或组合成一个没有重复值的单个数组。所以我们可以使用 Union()方法来完成这个任务。此方法通过移除两个数组中的重复元素来组合两个数组。如果一个数组中有两个相同的元素，那么它将只取一次元素。

**语法:**

> first_array。联合(第二个数组)

**示例:**

```cs
Input : array1 = {22, 33, 21, 34, 56, 32}
         array2 = {24, 56, 78, 34, 22}
Output : New array = {22, 33, 21, 34, 56, 32, 24, 78}

Input  : array1 = {1}
         array2 = {2}
Output : New array = {1, 2}
```

## 方法

**1。**声明任意类型整数、字符串等的两个数组。

**2。**应用 Union()函数，使用 to array()函数转换为数组。

```cs
final = array1.Union(array2).ToArray();
```

**3。**现在使用 ForEach()函数迭代最终数组中的元素。

```cs
Array.ForEach(final, i => Console.WriteLine(i));
```

**4。**我们也可以使用 IEnumerable 方法迭代数组。

```cs
IEnumerable<int> final = array1.Union(array2);    
foreach (var in final)    
{    
    Console.WriteLine(i);    
} 
```

**例 1:**

## C#

```cs
// C# program to merge two array into a single
// array without duplicate elements
using System;
using System.Collections.Generic;
using System.Linq;

class GFG{

public static void Main()
{

    // Declare first array with integer numbers
    int[] array1 = { 22, 33, 21, 34, 56, 32 };

    // Declare second array with integer numbers
    int[] array2 = { 24, 33, 21, 34, 22 };

    // Displaying array 1
    Console.WriteLine("Array 1: ");

    foreach (int x1 in array1)
    {
        Console.WriteLine(x1);
    }

    // Displaying array 2
    Console.WriteLine("Array 2: ");

    foreach (int x2 in array2)
    {
        Console.WriteLine(x2);
    }

    // Combine the unique elements and convert into array
    var final = array1.Union(array2).ToArray();

    // Display the elements in the final array
    Console.WriteLine("New array:");
    Array.ForEach(final, i => Console.WriteLine(i));
}
}
```

**输出:**

```cs
Array 1: 
22
33
21
34
56
32
Array 2: 
24
33
21
34
22
New array:
22
33
21
34
56
32
24
```

**例 2:**

## C#

```cs
// C# program to merge two array into a single
// array without duplicate elements
using System;
using System.Collections.Generic;
using System.Linq;

class GFG{

public static void Main()
{

    // Declare first array with strings 
    string[] array1 = { "ojaswi", "gnanesh", "bobby" };    

    // Declare second array with also strings
    string[] array2 = { "rohith", "ojaswi", "bobby" };

    // Displaying array 1
    Console.WriteLine("Array 1: ");

    foreach (string x1 in array1)
    {
        Console.WriteLine(x1);
    }

    // Displaying array 2
    Console.WriteLine("\nArray 2: ");

    foreach (string x2 in array2)
    {
        Console.WriteLine(x2);
    }

    // Combine the unique elements and convert into array
    IEnumerable<string> final1 = array1.Union(array2); 

    Console.WriteLine("\nNew array:");

    // Display the elements in the final array
    foreach (var j in final1)    
    {    
        Console.WriteLine(j);    
    } 
}
}
```

**输出:**

```cs
Array 1: 
ojaswi
gnanesh
bobby

Array 2: 
rohith
ojaswi
bobby

New array:
ojaswi
gnanesh
bobby
rohith
```