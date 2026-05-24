# C# | Char.IsNumber()方法

> 原文: [https://www.geeksforgeeks.org/c-sharp-char-isnumber-method/](https://www.geeksforgeeks.org/c-sharp-char-isnumber-method/)

在 C# 中，`Char.IsNumber()` 是一个 `System.Char` 结构方法，用于检查 Unicode 字符是否可以**归类为数字**。有效数字将是 `UnicodeCategory.DecimalDigitNumber`、`UnicodeCategory.LetterNumber` 或 `UnicodeCategory.OtherNumber` 类别的成员。

通过向该方法传递不同类型和数量的参数，可以重载该方法。
*   `Char.IsNumber(Char)` 方法
*   `Char.IsNumber(String, Int32)` 方法

**注:** 与 `Char.IsDigit()` 的唯一区别是 `IsDigit()` 方法只会检查一个 Char 是否为基数-10 的数字。而 `IsNumber()` 方法将检查一个字符是否是十进制数字，数字是否包括字符、分数、下标、上标、罗马数字、货币记数器和圈数。

## Char.IsNumber(Char) 方法

此方法用于检查指定的 Unicode 字符是否与数字匹配。如果匹配，则返回真，否则返回假。

**语法:**

```cs
public static bool IsNumber(char ch);
```

**参数:**

> **ch** : 需要检查的 `System.Char` 类型的 Unicode 字符。

**返回类型:** 如果成功匹配任意数字，则返回真，否则返回假。这种方法的返回类型是 `System.Boolean`。

**示例:**

```cs
// C# program to illustrate the
// Char.IsNumber(Char) Method
using System;

class GFG {

// Main Method
    static public void Main()
    {

// Declaration of data type
        bool result;

// checking if 5 is a
        // number or not
        char ch1 = '5';
        result = Char.IsNumber(ch1);
        Console.WriteLine(result);

// checking if 'c' is a
        // number or not
        char ch2 = 'c';
        result = Char.IsNumber(ch2);
        Console.WriteLine(result);
    }
}
```

**Output:**

```cs
True
False
```

## Char.IsNumber(String, Int32) 方法

此方法用于检查指定位置的指定字符串是否与任何数字匹配。如果匹配，则返回真，否则返回假。

**语法:**

```cs
public static bool IsNumber(string str, int index);
```

**参数:**

> **str**: 是 `System.String` 类型的必输字符串，要评估的字符串。
> **index**: 是要比较的字符串中字符的位置，该参数的类型为 `System.Int32`。

**返回类型:** 如果该方法成功匹配指定字符串中指定索引处的任何数字，则返回真，否则返回假。这种方法的返回类型是 `System.Boolean`。

**异常:**

*   如果 `str` 的值为 `null`，则该方法将给出 `ArgumentNullException`。
*   如果 `index` 小于零或大于 `str` 中的最后一个位置，则该方法将给出 `ArgumentOutOfRangeException`。

**示例:**

```cs
// C# program to illustrate the
// Char.IsNumber(String, Int32) Method
using System;

class GFG {

// Main Method
    static public void Main()
    {

// Declaration of data type
        bool result;

// checking for number in a
        // string at a desired position
        string str1 = "GeeksforGeeks";
        result = Char.IsNumber(str1, 2);
        Console.WriteLine(result);

// checking for number in a
        // string at a desired position
        string str2 = "geeks5forgeeks";
        result = Char.IsNumber(str2, 5);
        Console.WriteLine(result);
    }
}
```

**Output:**

```cs
False
True
```

**参考:** [https://docs.microsoft.com/en-us/dotnet/api/system.char.isnumber?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.char.isnumber?view=netframework-4.7.2)