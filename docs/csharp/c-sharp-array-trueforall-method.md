# C# |数组。TrueForAll()方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-array-trueforall-method/](https://www.geeksforgeeks.org/c-sharp-array-trueforall-method/)

此方法用于确定数组中的每个元素是否都符合指定谓词定义的条件。
**语法:**

```cs
public static bool TrueForAll (T[] array, Predicate<T> match);
```

这里，T 是数组元素的类型。
**参数:**

> **数组:**它是一维的、从零开始的数组，用来检查条件。
> **匹配:**是谓词定义了检查元素的条件。

**返回值:**如果*数组*中的每个元素都符合指定谓词定义的条件，则该方法返回 *true* ，否则返回 false。如果数组中没有元素，返回值为*真*。
**异常:**如果*数组*为空**或者**匹配*为空*，则该方法抛出 **ArgumentNullException** 。
下面的程序说明了**数组的使用。** :
**例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// TrueForAll() method
using System;
using System.Collections.Generic;

public class GFG {

// Main Method
public static void Main()
{

    try {

        // Creating and initializing new the String
        String[] myArr = {"Sun", "Son", "Sue", "Shu"};

        // Display the values of the myArr.
        Console.WriteLine("Initial Array:");

        // calling the PrintIndexAndValues()
        // method to print
        PrintIndexAndValues(myArr);

        // getting the bool value
        // with required condition
        // using method TrueForAll()
        bool value = Array.TrueForAll(myArr, element => element.StartsWith("S",
                                                    StringComparison.Ordinal));

        // Checking the condition
        if (value)
            Console.Write("Every Element is satisfying condition");
        else
            Console.Write("Every Element is not satisfying condition");
    }
    catch (ArgumentException e) {

        Console.Write("Exception Thrown: ");
        Console.Write("{0}", e.GetType(), e.Message);
    }
}

// Defining the method
// PrintIndexAndValues
public static void PrintIndexAndValues(String[] myArr)
{
    for (int i = 0; i < myArr.Length; i++) {

        Console.WriteLine("{0}", myArr[i]);
    }
    Console.WriteLine();
}
}
```

**Output:** 

```cs
Initial Array:
Sun
Son
Sue
Shu

Every Element is satisfying condition
```