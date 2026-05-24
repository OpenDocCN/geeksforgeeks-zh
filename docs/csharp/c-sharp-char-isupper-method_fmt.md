# C# | Char.IsUpper()方法

> 原文: [https://www.geeksforgeeks.org/c-sharp-char-isupper-method/](https://www.geeksforgeeks.org/c-sharp-char-isupper-method/)

在 C# 中，`Char.IsUpper()` 是一个 `System.Char` 结构方法，用于检查 Unicode 字符是否可以归类为大写字母。有效的大写字母将是“Unicode 类别：大写字母”的成员。通过向该方法传递不同类型和数量的参数，可以重载该方法。

## Char.IsUpper(Char) 方法

此方法用于检查指定的 Unicode 字符是否匹配任何大写字母。如果匹配，则返回 `true`，否则返回 `false`。

**语法:**

```cs
public static bool IsUpper(char ch);
```

**参数:**

> **ch** : 需要检查的 `System.Char` 类型的 Unicode 字符。

**返回类型:** 如果成功匹配任意大写字母，则返回 `true`，否则返回 `false`。这种方法的返回类型是 `System.Boolean`。

**示例:**

```cs
// C# program to illustrate the
// Char.IsUpper(Char) Method
using System;

class GFG {

    // Main Method
    static public void Main()
    {
        // Declaration of data type
        bool result;

        // checking if G is a
        // uppercase letter or not
        char ch1 = 'G';
        result = Char.IsUpper(ch1);
        Console.WriteLine(result);

        // checking if 'g' is a
        // uppercase letter or not
        char ch2 = 'g';
        result = Char.IsUpper(ch2);
        Console.WriteLine(result);
    }
}
```

**Output:**

```cs
True
False
```

## Char.IsUpper(String, Int32) 方法

此方法用于检查指定位置的指定字符串是否与任何大写字母匹配。如果匹配，则返回 `true`，否则返回 `false`。

**语法:**

```cs
public static bool IsUpper(string str, int index);
```

**参数:**

> **str**: 是 `System.String` 类型的必选字符串，要评估的字符串。
> **index**: 是要比较的字符串中字符的位置，该参数的类型为 `System.Int32`。

**返回类型:** 如果该方法成功匹配指定字符串中指定索引处的任何大写字母，则返回 `true`，否则返回 `false`。这种方法的返回类型是 `System.Boolean`。

**异常:**

*   如果 `str` 的值为 `null`，则该方法将给出 `ArgumentNullException`。
*   如果 `index` 小于零或大于 `str` 中的最后一个位置，则该方法将给出 `ArgumentOutOfRangeException`。

**示例:**

```cs
// C# program to illustrate the
// Char.IsUpper(String, Int32) Method
using System;

class GFG {

    // Main Method
    static public void Main()
    {
        // Declaration of data type
        bool result;

        // checking for uppercase letter in
        // a string at a desired position
        string str1 = "GeeksForGeeks";
        result = Char.IsUpper(str1, 5);
        Console.WriteLine(result);

        // checking for uppercase letter in a
        // string at a desired position
        string str2 = "geeksforgeeks";
        result = Char.IsUpper(str2, 2);
        Console.WriteLine(result);
    }
}
```

**Output:**

```cs
True
False
```

**参考:** [https://docs.microsoft.com/en-us/dotnet/api/system.char.isupper?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.char.isupper?view=netframework-4.7.2)