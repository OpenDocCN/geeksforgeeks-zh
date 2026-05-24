# C# | Char。IsPunctuation()方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-char-is punction-method/](https://www.geeksforgeeks.org/c-sharp-char-ispunctuation-method/)

在 C# 中， ***Char。*T3 是一个*系统。Char* 结构方法，用于检查 Unicode 字符是否可以归类为标点符号。通过向该方法传递不同类型和数量的参数，可以重载该方法。**

***   Char.*   Charging method.**

方法

#### 夏尔。计费方法

此方法用于检查指定的 Unicode 字符是否与任何标点符号匹配。如果匹配，则返回真，否则返回假。

**语法:**

```cs
public static bool IsPunctuation(char ch);

```

**参数:**

> **ch** :是需要比较的 *System.char* 类型的 Unicode 字符。

**返回类型:**如果成功匹配任意标点符号，则返回 True，否则返回 False。这种方法的返回类型是*系统。布尔*。

**示例:**

```cs
// C# program to illustrate the
// Char.IsPunctuation(Char) Method
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // Declaration of data type
        bool result;

        // checking if dot(.)
        // is a punctuation mark
        char ch1 = '.';
        result = Char.IsPunctuation(ch1);
        Console.WriteLine(result);

        // checking if semi-colon( ; )
        // is a punctuation mark
        char ch2 = ';';
        result = Char.IsPunctuation(ch2);
        Console.WriteLine(result);

        // checking if comma (, )
        // is a punctuation mark
        char ch3 = ', ';
        result = Char.IsPunctuation(ch3);
        Console.WriteLine(result);

        // checking if 'g' is
        // a punctuation mark
        char ch5 = 'g';
        result = Char.IsPunctuation(ch5);
        Console.WriteLine(result);
    }
}
```

**Output:**

```cs
True
True
True
False

```

#### 夏尔。IsPunctuation(字符串，Int32)方法

此方法用于检查指定位置的指定字符串是否与任何标点符号匹配。如果匹配，则返回真，否则返回假。

**语法:**

```cs
public static bool IsPunctuation(string str, int index);

```

**参数:**

> **字符串:**是*系统的必输字符串。要比较的字符串*类型。
> **索引:**是要比较的字符串中字符的位置，该参数的类型为 *System。Int32* 。

**返回类型:**如果成功匹配指定字符串中指定索引处的标点符号，则该方法返回 True，否则返回 False。这种方法的返回类型是*系统。布尔*。

**异常:**

*   如果 *str* 的值为 *null* ，则该方法将给出 **ArgumentNullException**
*   如果*索引*小于零或大于*字符串*中的最后一个位置，则该方法将给出**argumentout of rangerexception**。

**示例:**

```cs
// C# program to illustrate the
// Char.IsPunctuation(String, Int32) Method
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // Declaration of data type
        bool result;

        // checking for punctuation
        // in a string at specific location
        string str1 = "GeeksforGeeks";
        result = Char.IsPunctuation(str1, 2);
        Console.WriteLine(result);

        // checking for punctuation
        // in a string at specific location
        string str2 = "www.geeksforgeeks.org";
        result = Char.IsPunctuation(str2, 3);
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