# C# |隐式类型化数组

> 原文:[https://www . geeksforgeeks . org/c-sharp-隐式类型化-数组/](https://www.geeksforgeeks.org/c-sharp-implicitly-typed-arrays/)

隐式类型的[数组](https://www.geeksforgeeks.org/c-sharp-arrays/)是那些数组类型是从数组初始值中指定的元素推导出来的数组。隐式类型的数组类似于 [***隐式类型的变量***](https://www.geeksforgeeks.org/c-implicitly-typed-local-variables-var/) 。通常，查询表达式中使用隐式类型的数组。
**关于隐式类型数组的要点:**

*   在 C# 中，隐式类型化数组不包含任何特定的数据类型。
*   在隐式类型数组中，当用户用任何数据类型初始化数组时，编译器会自动将这些数组转换为该数据类型。
*   隐式类型的数组通常使用 **var** 关键字声明，这里 var 不跟在[]。例如:

```cs
var iarray = new []{1, 2, 3};
```

*   所有类型的数组，如一维数组、多维数组和交错数组等。可以创建为隐式类型的数组。
*   在 C# 中，需要初始化隐式类型的数组，并且具有相同的数据类型。

**示例 1:** 下面的程序说明了如何使用一维隐式类型化数组。

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate
// 1-D implicitly typed array
using System;

public class GFG {

    // Main method
    static public void Main()
    {

        // Creating and initializing 1-D
        // implicitly typed array
        var author_names = new[] {"Shilpa", "Soniya",
                                  "Shivi", "Ritika"};

        Console.WriteLine("List of Authors is: ");

        // Display the data of the given array
        foreach(string data in author_names)
        {
            Console.WriteLine(data);
        }
    }
}
```

**Output:** 

```cs
List of Authors is: 
Shilpa
Soniya
Shivi
Ritika
```

**示例 2:** 下面的程序说明了多维隐式类型数组的使用。

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate
// 2-D implicitly typed array
using System;

public class GFG {

    // Main method
    static public void Main()
    {

        // Creating and initializing
        // 2-D implicitly typed array
        var language = new[, ] { {"C", "Java"},
                            {"Python", "C#"} };

        Console.WriteLine("Programming Languages: ");

        // taking a string
        string a;

        // Display the value at index [1, 0]
        a = language[1, 0];
        Console.WriteLine(a);

        // Display the value at index [0, 2]
        a = language[0, 1];
        Console.WriteLine(a);
    }
}
```

**Output:** 

```cs
Programming Languages: 
Python
Java
```

**示例 3:** 下面的代码演示了隐式类型的[交错](https://www.geeksforgeeks.org/c-jagged-arrays/)数组的使用。

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate
// implicitly typed jagged array
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Creating and initializing
        // implicitly typed jagged array
        var jarray = new[] {
            new[] { 785, 721, 344, 123 },
            new[] { 234, 600 },
            new[] { 34, 545, 808 },
            new[] { 200, 220 }
        };

        Console.WriteLine("Data of jagged array is :");

        // Display the data of array
        for (int a = 0; a < jarray.Length; a++) {
            for (int b = 0; b < jarray[a].Length; b++)
                Console.Write(jarray[a][b] + " ");
            Console.WriteLine();
        }
    }
}
```

**Output:** 

```cs
Data of jagged array is :
785 721 344 123 
234 600 
34 545 808 
200 220
```