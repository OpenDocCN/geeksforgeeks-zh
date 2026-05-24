# C# |数组。FindAll()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-array-findall-method/](https://www.geeksforgeeks.org/c-sharp-array-findall-method/)

此方法用于**检索所有与指定谓词定义的条件相匹配的元素**。
**语法:**

```cs
public static T[] FindAll (T[] array, Predicate match);
```

这里，T 是数组元素的类型。
**参数:**

> **数组:**是一维的，从零开始搜索的数组。
> **匹配:**是定义要搜索的元素的条件的谓词。

**返回值:**这个方法返回一个包含所有元素的数组，如果找到的话，这个数组符合指定谓词定义的条件。否则，它将返回一个空数组。
**异常:**如果*数组*为空或者*匹配*为空，该方法抛出 **ArgumentNullException** 。
下面的程序说明了**数组的使用。FindAll(T[]，谓词)方法:**
**例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// FindAll() method
using System;
using System.Collections.Generic;

public class GFG {

// Main Method
public static void Main()
{

    try {

        // Creating and initializing new the String
        String[] myArr = {"Sun", "Mon", "Tue", "Sat"};

        // Display the values of the myArr.
        Console.WriteLine("Initial Array:");

        // calling the PrintIndexAndValues()
        // method to print
        PrintIndexAndValues(myArr);

        // getting a element a with required
        // condition using method Find()
        String[] value = Array.FindAll(myArr,
               element => element.StartsWith("S",
               StringComparison.Ordinal));

        // Display the value
        // of the found element.
        Console.WriteLine("Elements are: ");

        // printing the Array of String
        PrintIndexAndValues(value);
    }
    catch (ArgumentNullException e) {

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
Mon
Tue
Sat

Elements are: 
Sun
Sat
```