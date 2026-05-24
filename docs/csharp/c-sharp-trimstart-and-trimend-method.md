# C# | TrimStart()和 TrimEnd()方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-trim start-and-trimend-method/](https://www.geeksforgeeks.org/c-sharp-trimstart-and-trimend-method/)

#### 先决条件:[c# 中的 Trim()方法](https://www.geeksforgeeks.org/c-trim-method/)

在[**c#**](https://www.geeksforgeeks.org/introduction-to-c-sharp/)***TrimStart()***&***TrimEnd()***都是这种串法。 **TrimStart()** 方法用于从当前字符串对象的**开始删除数组中指定的一组字符的出现。 **TrimEnd()** 方法用于从当前字符串对象的**结尾**中删除数组中指定的一组字符的出现。**

【TrimStart()方法的语法:

```cs
public string TrimStart(params char[] trimChars)
```

**曲美()方法的语法:**

```cs
public string TrimEnd(params char[] trimChars)
```

**说明:**两种方法都将 Unicode 字符数组或 null 作为参数。Null 是因为 [**params**](https://www.geeksforgeeks.org/c-params/) 关键字。这两种方法的返回类型值都是**系统。弦**。

以下是演示上述方法的程序:

*   **示例 1:** 演示**公共字符串 trim start(params char[]trim chars)**方法的程序。此方法从当前字符串对象中移除所有前导空格字符。遇到非空白字符时，每个前导修剪操作都会停止。例如，如果当前字符串是“*****0000abc000****”，而 trimChars 包含“*”和“0”，那么 TrimStart 方法返回“abc000****”。

## C#

```cs
// C# program to illustrate the
// TrimStart() method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // string to be trimmed
        string s1 = "*****0000abc000****";

        char[] charsToTrim1 = { '*', '0' };

        // string to be trimmed
        string s2 = "  abc";
        string s3 = "  -GFG-";
        string s4 = "  GeeksforGeeks";

        // Before TrimStart method call
        Console.WriteLine("Before:");
        Console.WriteLine(s1);
        Console.WriteLine(s2);
        Console.WriteLine(s3);
        Console.WriteLine(s4);

        Console.WriteLine("");

        // After TrimStart method call
        Console.WriteLine("After:");

        // argument as char array
        Console.WriteLine(s1.TrimStart(charsToTrim1));

        // if there is no argument then it
        // takes default as null, ' ',
        // '\t', '\r'
        Console.WriteLine(s2.TrimStart());

        // White space is not remove
        Console.WriteLine(s3.TrimStart('-'));

        // not take char array but Argument only character
        Console.WriteLine(s4.TrimStart(' ', 'G', 'e', 'k', 's'));
    }
}
```

**Output:** 

```cs
Before:
*****0000abc000****
  abc
  -GFG-
  GeeksforGeeks

After:
abc000****
abc
  -GFG-
forGeeks
```

*   **示例 2:** 演示**公共字符串 TrimEnd(params char[]trimChars)**方法的程序。此方法移除参数列表中出现的所有尾随字符。当遇到非空白字符时，每个尾部修剪操作都会停止。例如，如果当前字符串是“*****0000abc000****”，而 trimChars 包含“*”和“0”，那么 TrimEnd 方法返回“*****0000abc”。

## C#

```cs
// C# program to illustrate the
// TrimEnd() method
using System;

class GFG {

     // Main Method
     public static void Main()
    {

        // String to be trimmed
        string s1 = "*****0000abc000****";

        char[] charsToTrim1 = { '*', '0'};

        // string to be trimmed
        string s2 = "abc  ";
        string s3 = "  -GFG-  ";
        string s4 = "  GeeksforGeeks";

        // Before TrimEnd method call
        Console.WriteLine("Before:");
        Console.WriteLine(s1);
        Console.WriteLine(s2);
        Console.WriteLine(s3);
        Console.WriteLine(s4);

        Console.WriteLine("");

        // After TrimEnd method call
        Console.WriteLine("After:");

        // argument as char array
        Console.WriteLine(s1.TrimEnd(charsToTrim1));

        // if there is no argument then it
        // takes default as null, ' ',
        // '\t', '\r'
        Console.WriteLine(s2.TrimEnd());

        // White space is not remove
        Console.WriteLine(s3.TrimEnd('-'));

        // not take char array but
        // Argument only character
        Console.WriteLine(s4.TrimEnd(' ','G','e','k','s'));
       }
}
```

**Output:** 

```cs
Before:
*****0000abc000****
abc  
  -GFG-  
  GeeksforGeeks

After:
*****0000abc
abc
  -GFG-  
  Geeksfor
```

**注意:**如果在方法的参数列表中没有参数传递，那么**空值、制表符、回车符和空格**将从当前字符串对象的开始(对于 TrimStart()方法)和结束(对于 TrimEnd()方法)中自动移除。如果任何参数将传递给这两个方法，那么唯一指定的字符(作为参数传递)将从当前字符串对象中移除。如果空值、制表符、回车符和空格没有在这两种方法的参数列表中指定，它们将不会自动删除。

**参考文献:**

*   [https://msdn。微软。com/en-us/library/system 字符串。修剪开始](https://msdn.microsoft.com/en-us/library/system.string.trimstart(v=vs.110).aspx)
*   [https://msdn。微软。com/en-us/library/system 字符串。修剪端](https://msdn.microsoft.com/en-us/library/system.string.trimend(v=vs.110).aspx)