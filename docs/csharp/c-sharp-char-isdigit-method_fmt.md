# C# | Char.IsDigit() 方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-char-isdigit-method/](https://www.geeksforgeeks.org/c-sharp-char-isdigit-method/)

在 C# 中，`Char.IsDigit()` 是一个 `System.Char` 结构方法，用于检查 Unicode 字符是否可以归类为十进制数字（基数 10）。有效数字将是 Unicode 类别中“十进制数字”类别的成员。通过向该方法传递不同类型和数量的参数，可以重载该方法。

- `Char.IsDigit(Char)` 方法
- `Char.IsDigit(String, Int32)` 方法

## Char.IsDigit(Char) 方法

此方法用于检查指定的 Unicode 字符是否与十进制数字匹配。如果匹配，则返回 `true`，否则返回 `false`。

**语法：**

```cs
public static bool IsDigit(char ch);
```

**参数：**

> **ch**：需要检查的 `System.Char` 类型的 Unicode 字符。

**返回类型：** 如果成功匹配任意十进制数，则返回 `true`，否则返回 `false`。这种方法的返回类型是 `System.Boolean`。

**示例：**

```cs
// C# program to illustrate the
// Char.IsDigit(Char) Method
using System;

class GFG {

    // Main Method
    static public void Main()
    {
        // Declaration of data type
        bool result;

        // checking if 5
        // is a digit or not
        char ch1 = '5';
        result = Char.IsDigit(ch1);
        Console.WriteLine(result);

        // checking if 'c'
        // is a digit
        char ch2 = 'c';
        result = Char.IsDigit(ch2);
        Console.WriteLine(result);
    }
}
```

**输出：**

```cs
True
False
```

## Char.IsDigit(String, Int32) 方法

此方法用于检查指定位置的指定字符串中的字符是否与任何十进制数字匹配。如果匹配，则返回 `true`，否则返回 `false`。

**语法：**

```cs
public static bool IsDigit(string str, int index);
```

**参数：**

> **str**：是 `System.String` 类型的必输字符串，要评估的字符串。
> **index**：是要比较的字符串中字符的位置，该参数的类型为 `System.Int32`。

**返回类型：** 如果该方法成功匹配指定字符串中指定索引处的任何十进制数字，则返回 `True`，否则返回 `False`。这种方法的返回类型是 `System.Boolean`。

**异常：**

- 如果 `str` 的值为 `null`，则该方法将给出 `ArgumentNullException`。
- 如果 `index` 小于零或大于 `str` 中的最后一个位置，则该方法将给出 `ArgumentOutOfRangeException`。

**示例：**

```cs
// C# program to illustrate the
// Char.IsDigit(String, Int32) Method
using System;

class GFG {

    // Main Method
    static public void Main()
    {
        // Declaration of data type
        bool result;

        // checking for decimal digit in
        // a string at a desired position
        string str1 = "GeeksforGeeks";
        result = Char.IsDigit(str1, 2);
        Console.WriteLine(result);

        // checking for decimal digit in a
        // string at a desired position
        string str2 = "geeks5forgeeks";
        result = Char.IsDigit(str2, 5);
        Console.WriteLine(result);
    }
}
```

**输出：**

```cs
False
True
```

**参考：** [https://docs.microsoft.com/en-us/dotnet/api/system.char.isdigit?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.char.isdigit?view=netframework-4.7.2)