# C# |在不使用第三个用户定义变量的情况下交换两个字符串

> 原文:[https://www . geeksforgeeks . org/c-sharp-swap-不使用第三用户定义变量的两个字符串/](https://www.geeksforgeeks.org/c-sharp-swap-two-strings-without-using-third-user-defined-variable/)

给定两个字符串变量 a 和 b，在 C# 中交换这些变量而不使用临时变量或第三个变量。允许使用库方法。

**示例:**

```cs
Input:
a = "Hello"
b = "World"

Output:
Strings before swap: a = Hello and b = World
Strings after swap: a = World and b = Hello
```

思路是先做字符串拼接，然后用**[【Substring()](https://www.geeksforgeeks.org/c-substring-method/)**的方法来执行这个操作。Substring()方法有两种形式，如下所示:

*   **[弦。子串方法(startIndex)](https://www.geeksforgeeks.org/c-substring-method/)** :此方法用于从字符串的当前实例中检索子串。参数“开始索引”将指定子字符串的开始位置，然后子字符串将继续到字符串的末尾。
*   **[弦。Substring 方法(int startIndex，int length)](https://www.geeksforgeeks.org/c-substring-method/)** :该方法用于提取从参数 startIndex 描述的指定位置开始，具有指定长度的子串。如果 startIndex 等于字符串长度，而参数长度为零，那么它将不返回任何子字符串。

 **算法:**

```cs
1) Append second string to first string and 
   store in first string:
   a = a + b

2) Call the Substring Method (int startIndex, int length)
   by passing startindex as 0 and length as,
   a.Length - b.Length:
   b = Substring(0, a.Length - b.Length);

3) Call the Substring Method(int startIndex) by passing 
   startindex as b.Length as the argument to store the 
   value of initial b string in a
   a = Substring(b.Length);

```

```cs
// C# program to swap two strings
// without using a temporary variable.
using System;

class GFG {

    // Main Method
    public static void Main(String[] args)
    {
        // Declare two strings
        String a = "Hello";
        String b = "Geeks";

        // Print String before swapping
        Console.WriteLine("Strings before swap: a =" + 
                          " " + a + " and b = " + b);

        // append 2nd string to 1st
        a = a + b;

        // store initial string a in string b
        b = a.Substring(0, a.Length - b.Length);

        // store initial string b in string a
        a = a.Substring(b.Length);

        // print String after swapping
        Console.WriteLine("Strings after swap: a =" +
                          " " + a + " and b = " + b);
    }
}
```

**输出:**

```cs
Strings before swap: a = Hello and b = Geeks
Strings after swap: a = Geeks and b = Hello

```