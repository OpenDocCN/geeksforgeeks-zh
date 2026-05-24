# C# |检查每个 List 元素是否匹配谓词条件

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-every-list-element-match-the-predicate-conditions/](https://www.geeksforgeeks.org/c-sharp-check-if-every-list-element-matches-the-predicate-conditions/)

**列表< T >。TrueForAll(谓词< T > )** 用于检查列表< T >中的每个元素是否符合指定谓词定义的条件。

**语法:**

```cs
public bool TrueForAll (Predicate<T> match);
```

**参数:**

> **匹配:**是谓词< T >委托定义了检查元素的条件。

**返回值:**如果列表< T >中的每个元素都符合指定谓词定义的条件，则该方法返回 *true* ，否则返回 *false* 。如果列表没有元素，返回值为*真*。

**异常:**如果匹配为空，该方法将给出 *ArgumentNullException* 。

以下程序说明了**列表< T >的使用。TrueForAll(谓词< T >)方法:**

**例 1:**

```cs
// C# Program to check if every element 
// in the List matches the conditions 
// defined by the specified predicate
using System; 
using System.Collections; 
using System.Collections.Generic; 

class Geeks { 

    // function which checks whether an 
    // element is even or not. Or you can 
    // say it is the specified condition 
    private static bool isEven(int i) 
    { 
        return ((i % 2) == 0); 
    } 

    // Main Method 
    public static void Main(String[] args) 
    { 

        // Creating a List<T> of Integers 
        List<int> firstlist = new List<int>(); 

        // Adding elements to List 
        for (int i = 0; i <= 10; i+=2) { 
            firstlist.Add(i); 
        } 

        Console.WriteLine("Elements Present in List:\n"); 

        // Displaying the elements of List 
        foreach(int k in firstlist) 
        { 
            Console.WriteLine(k); 
        } 

        Console.WriteLine(" "); 

        Console.Write("Result: "); 

        // Checks if all the elements of firstlist
        // matches the condition defined by predicate 
        Console.WriteLine(firstlist.TrueForAll(isEven)); 
    } 
} 
```

**Output:**

```cs
Elements Present in List:

0
2
4
6
8
10

Result: True

```

**例 2:**

```cs
// C# Program to check if every element 
//in the List matches the conditions 
//defined by the specified predicate
using System;
using System.Collections; 
using System.Collections.Generic;

public class Example
{
    public static void Main()
    {
        List<string> lang = new List<string>();

        lang.Add("C# language");
        lang.Add("C++ language");
        lang.Add("Java language");
        lang.Add("Pyhton language");
        lang.Add("Ruby language");

        Console.WriteLine("Elements Present in List:\n"); 

        foreach(string language in lang)
        {
            Console.WriteLine(language);
        }

        Console.WriteLine(" "); 

        Console.Write("TrueForAll(EndsWithLanguage): ");

        // Checks if all the elements of lang
        // matches the condition defined by predicate 
        Console.WriteLine(lang.TrueForAll(EndsWithLanguage));
    }

    // Search predicate returns 
    // true if a string ends in "language".
    private static bool EndsWithLanguage(String s)
    {
        return s.ToLower().EndsWith("language");
    }
}
```

**Output:**

```cs
Elements Present in List:

C# language
C++ language
Java language
Pyhton language
Ruby language

TrueForAll(EndsWithLanguage): True

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . list-1 . true for all？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.trueforall?view=netframework-4.7.2)