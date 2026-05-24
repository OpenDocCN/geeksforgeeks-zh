# c# | isnullorhitespace()方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-isnullorhitespace-method/](https://www.geeksforgeeks.org/c-sharp-isnullorwhitespace-method/)

在 C# 中， ***是一个字符串方法。用于检查指定的字符串是**空**还是只包含**空格**字符。如果一个字符串没有被赋值或者被显式赋值为 null，那么它将为 null。***

**语法:**

```cs
public static bool IsNullOrWhiteSpace(String str)  

```

**说明:**该方法将采用类型为**系统的参数。字符串**并且这个方法将返回一个布尔值。如果方法的参数列表为空或*字符串。空*，或者只包含空白字符，则返回真，否则返回假。

**例:**

```cs
Input : str  = null         // initialize by null value
        String.IsNullOrWhiteSpace(str)
Output: True

Input : str  = " "  // initialize by whitespace
        String.IsNullOrWhiteSpace(str)
Output: True

```

**程序:**演示 IsNullOrWhiteSpace()方法的工作原理:

```cs
// C# program to illustrate 
// IsNullOrWhiteSpace() Method
using System;
class Geeks {

    // Main Method
    public static void Main(string[] args)
    {
        string s1 = null;

        // for null value always return true
        bool b1 = String.IsNullOrWhiteSpace(s1);
        Console.WriteLine(b1);

        string s2 = " ";

        // for whitespace value always return true
        bool b2 = String.IsNullOrWhiteSpace(s2);
        Console.WriteLine(b2);

        string s4 = " \n ";

        // for new line value return true
        bool b4 = String.IsNullOrWhiteSpace(s4);
        Console.WriteLine(b4);

        string s5 = "\t";

        // for tab value return true
        bool b5 = String.IsNullOrWhiteSpace(s5);
        Console.WriteLine(b5);

        string s6 = "\r";

        // for carriage Return value return true
        bool b6 = String.IsNullOrWhiteSpace(s6);
        Console.WriteLine(b6);

        string s7 = "GFG";

        // for s7 it return False
        bool b7 = String.IsNullOrWhiteSpace(s7);
        Console.WriteLine(b7);
    }
}
```

**Output:**

```cs
True
True
True
True
True
False

```

**注:**isnullorhitespace()方法有一个备选代码如下:

```cs
return String.IsNullOrEmpty(str) || str.Trim().Length == 0;

```

**程序:**演示 IsNullOrEmpty()方法的替代方案

```cs
// C# program to illustrate the 
// similar code for IsNullOrWhiteSpace()
using System;
class Geeks {

    // similar code to 
    // IsNullOrWhiteSpace()
    public static bool check(string str)
    {
        return(String.IsNullOrEmpty(str) || 
              str.Trim().Length == 0) ? true : false;
    }

    // Main Method
    public static void Main(string[] args)
    {
        string s1 = "GeeksforGeeks";
        string s2 = " "; 
        string s3 = null;
        string s4 = " \n ";

        bool b1 = check(s1);
        bool b2 = check(s2);
        bool b3 = check(s3);
        bool b4 = check(s4);

        // To display result
        Console.WriteLine(b1);
        Console.WriteLine(b2);
        Console.WriteLine(b3);
        Console.WriteLine(b4);
    }
}
```

**输出:**

```cs
False
True
True
True

```

**参考:**T2