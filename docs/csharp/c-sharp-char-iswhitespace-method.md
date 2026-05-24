# C# | Char。IsWhiteSpace()方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-char-ishitespace-method/](https://www.geeksforgeeks.org/c-sharp-char-iswhitespace-method/)

在 C# 中， ***Char。*** 是一个*系统。Char* 结构方法，用于检查 Unicode 字符是否为空白。空白字符包括类别*空间分隔符*、*行分隔符*、*段落分隔符*等 Unicode 字符。通过向该方法传递不同类型和数量的参数，可以重载该方法。

***   -什么.石泰斯 pace(坦克)-什么T4【Char】。ishitespace(String，Int32)方法**

#### 夏尔。IsWhiteSpace(字符)方法

此方法用于检查指定的 Unicode 字符是否可以归类为空白字符。如果它可以被归类为空白，那么它返回真，否则返回假。

**语法:**

```cs
public static bool IsWhiteSpace(char ch);
```

**参数:**

> **ch** :要求是*系统. char* 类型的 Unicode 字符，需要检查空格。

**返回类型:**如果指定的 Unicode 字符是空白字符，则该方法返回 True，否则返回 False。这种方法的返回类型是*系统。布尔*。

**示例:**

```cs
// C# program to illustrate the
// Char.IsWhiteSpace(Char) Method
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // Declaration of data type
        bool result;

        // checking if space
        // is a whitespace
        char ch1 = ' ';
        result = Char.IsWhiteSpace(ch1);
        Console.WriteLine(result);

        // checking if carriage return
        // is a whitespace
        char ch2 = '\n';
        result = Char.IsWhiteSpace(ch2);
        Console.WriteLine(result);

        // checking if hyphen
        // is a whitespace
        char ch3 = '-';
        result = Char.IsWhiteSpace(ch3);
        Console.WriteLine(result);
    }
}
```

**Output:**

```cs
True
True
False

```

#### 夏尔。IsWhiteSpace(字符串，Int32)方法

此方法用于检查指定字符串中指定位置的字符是否可以归类为空白。当字符为空白字符时，返回真，否则返回假。

**语法:**

```cs
public static bool Char.IsWhiteSpace(string str, int index);
```

**参数:**

> **字符串:**是*系统的必输字符串。字符串*要检查字符的类型。
> **索引:**是指定字符串中字符的位置，该参数的类型为 *System。Int32* 。

**返回类型:**如果指定字符串中指定索引处的字符可以归类为空白，则该方法返回真，否则返回假。这种方法的返回类型是*系统。布尔*。

**示例:**

```cs
// C# program to illustrate the
// Char.IsWhiteSpace (String, Int32) Method
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // Declaration of data type
        bool result;

        // checking for whitespace
        // in a string
        string str1 = "GeeksforGeeks";
        result = Char.IsWhiteSpace(str1, 2);
        Console.WriteLine(result);

        // checking for whitespace
        // in a string
        string str2 = "Geeks For Geeks";
        result = Char.IsWhiteSpace(str2, 5);
        Console.WriteLine(result);
    }
}
```

**Output:**

```cs
False
True

```

**参考:**T2？视图=netframework-4.7.2