# 检查指定类型是否为数组的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-check-a-specified-type-is-a-array-or-not/](https://www.geeksforgeeks.org/c-sharp-program-to-check-a-specified-type-is-an-array-or-not/)

在 C# 中，数组是一组由通用名称引用的同构元素。因此，在本文中，我们将讨论如何检查变量是否为数组类型。为了完成这个任务，我们使用类型类的 **IsArray** 属性。此属性用于确定指定的类型是否为数组。如果指定的类型是数组，IsArray 属性将返回 true。否则，它将返回 false。

**语法:**

```cs
public bool IsArray{get;}
```

**返回:**如果值为数组，则返回真，否则返回假。

**接近**

> *   Import system. Reflection namespace.
> *   Declare an array of data type n.
> *   IsArray is a method to check whether the type is an array, and GetType () method is also used. The GetType () method gets the type of the variable.
> 
> ```cs
> array.GetType().IsArray
> ```
> 
> *   If the condition is true, "Type is array" will be displayed; if the condition is false, "Type is not array" will be displayed.

**例 1:**

## C#

```cs
// C# program to determine whether the
// specified type is an array or not
using System;
using System.Reflection;

class GFG{

static void Main()
{

    // Declare an array with size 5
    // of integer type
    int[] array1 = new int[5];

    // Check whether the variable is array or not
    // Using IsArray property
    if (array1.GetType().IsArray == true)
    {
        Console.WriteLine("Type is array");
    }
    else
    {
        Console.WriteLine("Type is not array");
    }
}
}
```

**输出:**

```cs
Type is array
```

**例 2:**

## C#

```cs
// C# program to determine whether the
// specified type is an array or not
using System;
using System.Reflection;

class GFG{

static void Main()
{

    // Declare and initializing variables
    int array1 = 45;
    string array2 = "GeeksforGeeks";
    int[] array3 = new int[3];
    double[] array4 = { 2.3, 4.5, 0.33 };

    // Check whether the variable is of array type or not
    // Using IsArray property
    Console.WriteLine("Is the type of array1 varaiable is array?" +
                      array1.GetType().IsArray);
    Console.WriteLine("Is the type of array2 varaiable is array?" +
                      array2.GetType().IsArray);
    Console.WriteLine("Is the type of array2 varaiable is array?" +
                      array3.GetType().IsArray);
    Console.WriteLine("Is the type of array2 varaiable is array?" +
                      array4.GetType().IsArray);
}
}
```

**输出:**

```cs
Is the type of array1 varaiable is array?False
Is the type of array2 varaiable is array?False
Is the type of array2 varaiable is array?True
Is the type of array2 varaiable is array?True
```