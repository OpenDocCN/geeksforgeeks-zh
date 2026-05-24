# C# `Char.IsSeparator()` 方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-char-isseparator-method/](https://www.geeksforgeeks.org/c-sharp-char-isseparator-method/)

在 C# 中，`Char.IsSeparator()` 是一个 `System.Char` 结构方法，用于检查 Unicode 字符是否可以归类为分隔符。通过向该方法传递不同类型和数量的参数，可以重载该方法。

## 方法重载

1.  `Char.IsSeparator(char)` 方法
2.  `Char.IsSeparator(string, int)` 方法

### `Char.IsSeparator(char)` 方法

此方法用于检查指定的 Unicode 字符是否与任何分隔符匹配。如果匹配，则返回 `true`，否则返回 `false`。

**语法：**

```cs
public static bool IsSeparator(char ch);
```

**参数：**

> `ch`：需要检查的 `System.Char` 类型的 Unicode 字符。

**返回类型：** 如果成功匹配任意分隔符，则返回 `true`，否则返回 `false`。这种方法的返回类型是 `System.Boolean`。

**例：**

```cs
// C# program to illustrate the
// Char.IsSeparator(Char) Method
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // Declaration of data type
        bool result;

        // checking if space
        // is a separator
        char ch1 = ' ';
        result = Char.IsSeparator(ch1);
        Console.WriteLine(result);

        // checking if dot(.)
        // is a separator
        char ch2 = '.';
        result = Char.IsSeparator(ch2);
        Console.WriteLine(result);
    }
}
```

**Output：**

```cs
True
False
```

### `Char.IsSeparator(string, int)` 方法

此方法用于检查指定位置的指定字符串是否与任何分隔符匹配。如果匹配，则返回 `true`，否则返回 `false`。

**语法：**

```cs
public static bool IsSeparator(string str, int index);
```

**参数：**

> `str`：是 `System.String` 类型的要评估的字符串。
> `index`：是要比较的字符串中字符的位置，该参数的类型为 `System.Int32`。

**返回类型：** 如果该方法成功匹配指定字符串中指定索引处的任何分隔符，则返回 `true`，否则返回 `false`。这种方法的返回类型是 `System.Boolean`。

**例外：**

*   如果 `str` 的值为 `null`，则该方法将给出 `ArgumentNullException`。
*   如果 `index` 小于零或大于 `str` 中的最后一个位置，则该方法将给出 `ArgumentOutOfRangeException`。

**例：**

```cs
// C# program to illustrate the
// Char.IsSeparator(String, Int32) Method
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // Declaration of data type
        bool result;

        // checking for separator
        // in a string at a desired position
        string str1 = "GeeksforGeeks";
        result = Char.IsSeparator(str1, 2);
        Console.WriteLine(result);

        // checking for separator
        // in a string at a desired position
        string str2 = "geeks for geeks";
        result = Char.IsSeparator(str2, 5);
        Console.WriteLine(result);
    }
}
```

**Output：**

```cs
False
True
```

**参考：** [https://docs.microsoft.com/en-us/dotnet/api/system.char.isseparator?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.char.isseparator?view=netframework-4.7.2)