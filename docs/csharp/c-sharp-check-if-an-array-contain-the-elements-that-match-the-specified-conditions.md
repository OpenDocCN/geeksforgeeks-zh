# C# |检查数组是否包含符合指定条件的元素

> 原文:[https://www . geeksforgeeks . org/c-sharp-check-if-array-contain-the-elements-match-the-specific-conditions/](https://www.geeksforgeeks.org/c-sharp-check-if-an-array-contain-the-elements-that-match-the-specified-conditions/)

**阵列。Exists(T[]，谓词< T >)方法**用于检查指定数组是否包含与指定谓词定义的条件相匹配的元素。

**语法:**

```cs
public static bool Exists<T> (T[] array, Predicate<T> match);
```

**参数:**

> **数组:**是一维的，从零开始搜索的数组。
> **匹配:**它是一个谓词，定义了要搜索的元素的条件。其中 T 是数组中元素的类型。

**返回值:**该方法的返回类型为**系统。布尔**。如果*数组*包含一个或多个与指定谓词定义的条件相匹配的元素，则返回 **true** 。否则，返回**假**。

**异常:**如果*数组*的值为空，或者*匹配*的值为空，该方法将给出 *ArgumentNullException* 。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# program to illustrate the 
// Array.Exists(T[], Predicate<T>) Method
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Create and initialize array
        string[] language = {"Ruby", "C", "C++", "Java",
                             "Perl", "C#", "Python", "PHP"};

        // Display language array
        Console.WriteLine("Display the array:");
        foreach(string i in language)
        {
            Console.WriteLine(i);
        }

        // Display and check the given elements
        // present in the array or not

        // Using Exists() method
        Console.WriteLine("Is Ruby part of language: {0}",
                          Array.Exists(language, element => element == "Ruby"));

        Console.WriteLine("Is VB part of language: {0}",
                          Array.Exists(language, element => element == "VB"));
    }
}
```

**Output:**

```cs
Display the array:
Ruby
C
C++
Java
Perl
C#
Python
PHP
Is Ruby part of language: True
Is VB part of language: False

```

**例 2:**

```cs
// C# program to illustrate the 
// Array.Exists(T[], Predicate<T>) Method
using System;

public class GFG {

// Main method
static public void Main()
{

    // Create and initialize array
    string[] ds = {"Array", "Queue", "LinkedList",
                               "Stack", "Graph" };

    // Display ds array
    Console.WriteLine("Given Array: ");

    foreach(string i in ds)
    {
        Console.WriteLine(i);
    }

    // Display and check the given elements with the
    // specified letter is present in the array or not
    // Using Exists() method
    Console.WriteLine("Is element start with L letter is present in array: {0}",
                      Array.Exists(ds, element => element.StartsWith("L")));

    Console.WriteLine("Is element start with O letter is present in array: {0}",
                      Array.Exists(ds, element => element.StartsWith("O")));
}
}
```

**Output:**

```cs
Given Array: 
Array
Queue
LinkedList
Stack
Graph
Is element start with L letter is present in array: True
Is element start with O letter is present in array: False

```

**注:**此法为 O(n)运算，其中 **n** 为数组长度。

**参考:**[https://docs . Microsoft . com/en-us/dotnet/API/system . array . exists？视图= netcore-2.1 # 定义](https://docs.microsoft.com/en-us/dotnet/api/system.array.exists?view=netcore-2.1# definition)