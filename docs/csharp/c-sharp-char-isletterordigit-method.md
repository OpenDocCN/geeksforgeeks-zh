# C# | Char。方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-char-isletterordigit-method/](https://www.geeksforgeeks.org/c-sharp-char-isletterordigit-method/)

在 C# 中， ***Char。*** 是一个*系统。Char* 结构方法，用于检查一个 Unicode 字符是否可以归类为字母或十进制数字。有效字母和十进制数字将是*统一编码类别的成员:大写字母、小写字母、标题字母、修改字母、其他字母或十进制数字*类别。通过向该方法传递不同类型和数量的参数，可以重载该方法。

***   Char.T4【夏尔】法。**

方法

#### 夏尔。字符数字方法

此方法用于检查指定的 Unicode 字符是否匹配任何字母或十进制数字。如果匹配，则返回真，否则返回假。

**语法:**

```cs
public static bool IsLetterOrDigit(char ch);
```

**参数:**

> **ch** :需要检查的*系统. char* 类型的 Unicode 字符。

**返回类型:**如果成功匹配任何 Unicode 字母或十进制数字，则该方法返回 True，否则返回 False。这种方法的返回类型是**系统。布尔**。

**示例:**

```cs
// C# program to illustrate the
// Char.IsLetterOrDigit(Char) Method
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // Declaration of data type
        bool result;

        // checking if G is a
        // letter or decimal digit
        char ch1 = 'G';
        result = Char.IsLetterOrDigit(ch1);
        Console.WriteLine(result);

        // checking if '@' is a
        // letter or decimal digit
        char ch2 = '@';
        result = Char.IsLetterOrDigit(ch2);
        Console.WriteLine(result);
    }
}
```

**Output:**

```cs
True
False

```

#### 夏尔。IsLetterOrDigit(字符串，Int32)方法

此方法用于检查指定位置的指定字符串是否与任何字母或十进制数字匹配。如果匹配，则返回真，否则返回假。

**语法:**

```cs
public static bool IsLetterOrDigit(string str, int index);
```

**参数:**

> **字符串:**是*系统的必输字符串。要评估的字符串*类型。
> **索引:**是要比较的字符串中字符的位置，该参数的类型为 *System。Int32* 。

**返回类型:**如果成功匹配指定字符串中指定索引处的任何字母或十进制数字，则该方法返回 True，否则返回 False。这种方法的返回类型是*系统。布尔*。

**异常:**

*   如果 *str* 的值为 *null* ，则该方法将给出 **ArgumentNullException** 。
*   如果*索引*小于零或大于*字符串*中的最后一个位置，则该方法将给出**argumentout of rangerexception**。

**示例:**

```cs
// C# program to illustrate the
// Char.IsLetterOrDigit(String, Int32) Method
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // Declaration of data type
        bool result;

        // checking for letter or decimal digit
        // in a string at desired position
        string str1 = "Geeks46orGeeks";
        result = Char.IsLetterOrDigit(str1, 5);
        Console.WriteLine(result);

        // checking for letter or decimal digit
        // in a string at a desired position
        string str2 = "geeks%forgeeks";
        result = Char.IsLetterOrDigit(str2, 5);
        Console.WriteLine(result);
    }
}
```

**Output:**

```cs
True
False

```

**参考:**T2？视图=netframework-4.7.2