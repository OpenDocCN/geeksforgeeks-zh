# C# |数组。查找()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-array-find-method/](https://www.geeksforgeeks.org/c-sharp-array-find-method/)

此方法用于搜索与指定谓词定义的条件相匹配的元素，**返回整个数组中的第一个匹配项**。
**语法:**

```cs
public static T Find (T[] array, Predicate<T> match);
```

这里，T 是数组元素的类型。
**参数:**

> **数组:**是一维的，从零开始搜索的数组。
> **匹配:**是定义要搜索的元素的条件的谓词。

**返回值:**如果找到符合指定谓词定义的条件的第一个元素，则该方法返回该元素。否则，返回类型 t 的默认值。
**异常:**如果*数组*为空或者*匹配*为空，则该方法抛出 **ArgumentNullException** 。
下面的程序说明了**数组的使用。Find(T[]，谓词)方法:**
**例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// Array.Find(T[], Predicate<T>)
// Method
using System;
using System.Collections.Generic;

public class GFG {

    // Main Method
    public static void Main()
    {

        try {

            // Creating and initializing new the String
            String[] myArr = {"Sun", "Mon", "Tue", "Thu"};

            // Display the values of the myArr.
            Console.WriteLine("Initial Array:");

            // calling the PrintIndexAndValues()
            // method to print
            PrintIndexAndValues(myArr);

            // getting a element a with required
            // condition using method Find()
            string value = Array.Find(myArr,
                       element => element.StartsWith("S",
                       StringComparison.Ordinal));

            // Display the value of
            // the found element.
            Console.Write("Element: ");

            // printing the string
            // following the condition
            Console.Write("{0}", value);
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
Thu

Element: Sun
```