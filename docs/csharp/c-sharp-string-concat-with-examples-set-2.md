# C# |字符串 Concat 带示例| Set-2

> 原文:[https://www . geesforgeks . org/c-sharp-string-concat-with-examples-set-2/](https://www.geeksforgeeks.org/c-sharp-string-concat-with-examples-set-2/)

**弦。连接方法**用于连接一个或多个[字符串](https://www.geeksforgeeks.org/c-string/)的实例或一个或多个对象实例的值的[字符串](https://www.geeksforgeeks.org/c-string/)表示。它总是返回串联字符串。
这个方法可以通过传递不同类型和数量的参数来重载。Concat 方法的重载列表中共有 **11** 种方法，其中前 3 种在**[【Set-1】](https://www.geeksforgeeks.org/c-string-concat-with-examples-set-1/)**中讨论，其余的在 **Set-2、Set-3、Set-4** 中讨论。

##### 4\. 连接（字符串，字符串）

此方法用于连接字符串的两个不同实例。您也可以使用连接运算符( **+** )来连接字符串。

**注意:**如果数组包含空对象，则使用空字符串代替空对象。

**语法:**

```cs
public static string Concat (string strA, string strB);
```

**参数:**

> **strA:** 要连接的第一个字符串。
> **strB:** 第二串串联。

**返回值:**该方法的返回类型为**系统。弦**。这个方法返回一个字符串作为两个字符串连接的结果，即 *strA* 和 *strB* 。

**示例:**

```cs
// C# program to illustrate the use 
// of Concat(String, String ) Method
using System;

public class GFG {

    // Main Method
    static public void Main()
    {
        string strA = "Hello! ";
        string strB = "Geeks.";
        string str;

        // print all strings
        Console.WriteLine("String A is: {0}", strA);
        Console.WriteLine("String B is: {0}", strB);

        // Concatenate two different strings
        // into a single String
        // using  Concat(String, String ) Method
        str = String.Concat(strA, strB);

        Console.WriteLine("Concatenated string is: {0}", str);
    }
}
```

**输出:**

```cs
String A is: Hello! 
String B is: Geeks.
Concatenated string is: Hello! Geeks.

```

##### 5\. 连接（字符串，字符串，字符串）

此方法用于将三个不同的字符串连接成一个字符串。您也可以使用连接运算符( **+** )来连接字符串。

**注意:**如果数组包含空对象，则使用空字符串代替空对象。

**语法:**

```cs
public static string Concat (string strA, string strB, string strC);
```

**参数:**

> **strA:** 要连接的第一个字符串。
> **strB:** 第二串串联。
> **strC:** 要连接的第三个字符串。

**返回值:**该方法的返回类型为**系统。弦**。该方法返回一个由三个字符串串联而成的字符串，即 *strA* 、 *strB* 和 *strC* 。

**示例:**

```cs
// C# program to illustrate the 
// Concat(String, String, String) Method
using System;

class GFG {

    // Main Method
    static public void Main()
    {
        string strA = "Welcome ";
        string strB = "to ";
        string strC = "GFG. ";
        string str;

        // print all strings
        Console.WriteLine("String A is: {0}", strA);
        Console.WriteLine("String B is: {0}", strB);
        Console.WriteLine("String C is: {0}", strC);

        // Concatenate three different strings 
        // into a single String using the 
        // Concat(String, String, String ) Method
        str = String.Concat(strA, strB, strC);

        Console.WriteLine("Concatenated string is: {0}", str);
    }
}
```

**输出:**

```cs
String A is: Welcome 
String B is: to 
String C is: GFG.
Concatenated string is: Welcome to GFG. 

```

##### 6\. 连接（字符串[]）

此方法用于连接指定字符串数组的元素。

**语法:**

```cs
public static string Concat (params string[] items);
```

这里，*项*是字符串实例的数组。

**返回值:**该方法的返回类型为**系统。弦**。此方法返回项的串联元素。

**异常:**

*   如果给定字符串项的值为空，则该方法将给出 **ArgumentNullException** 。
*   如果数组内存不足，那么这个方法会给出 **OutOfMemoryException** 。

**示例:**

```cs
// C# program to illustrate the 
// Concat(string[]) Method
using System;

class GFG {

    // Main method
    public static void Main()
    {

        // array 
        string[] strA = {"Hey, ", "This ","is ", "C# ", "Tutorial."};

        // print elements of array
        foreach(string elements in strA)
        {
            Console.WriteLine("Elements of strA array : {0}", elements);
        }

        // concatenate the element of array
        // into single string
        // using Concat(string[]) Method
        Console.WriteLine("After Concatenation: {0}",
                                 string.Concat(strA));
    }
}
```

**输出:**

```cs
Elements of strA array : Hey, 
Elements of strA array : This 
Elements of strA array : is 
Elements of strA array : C# 
Elements of strA array : Tutorial.
After Concatenation: Hey, This is C# Tutorial.

```

**下一个:** [第三集](https://www.geeksforgeeks.org/c-string-concat-with-examples-set-3/)

**参考:**T2？视图=netframework-4.7.2