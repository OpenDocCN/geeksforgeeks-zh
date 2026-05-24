# C# Trim()方法

> 原文: [https://www.geeksforgeeks.org/c-sharp-trim-method/](https://www.geeksforgeeks.org/c-sharp-trim-method/)

C# `Trim()` 是一个字符串方法。此方法用于从当前字符串对象中移除所有前导和尾随空格字符。这个方法可以通过传递参数来重载。

## 语法

```cs
public string Trim()
// 或
public string Trim (params char[] trimChars)
```

## 说明

第一种方法不取任何参数，第二种方法取 Unicode 字符数组或 `null` 作为参数。`null` 是因为 `params` 关键字。`Trim()` 方法的返回类型是 `System.String`。

## 注意

如果在 `public string Trim()` 中没有传递参数，那么 `null`、`TAB`、回车和空格将自动删除，如果它们存在于当前字符串对象中的话。如果任何参数将传递到 `Trim()` 方法中，那么只有指定的字符（在 `Trim()` 方法中作为参数传递）将从当前字符串对象中移除。如果参数列表中未指定空值、制表符、回车符和空格，它们将不会自动删除。

下面是演示上述方法的程序：

### 示例 1

程序演示 `public string Trim()` 方法。`Trim` 方法从当前字符串对象中移除所有前导和尾随空格字符。当遇到非空白字符时，每个前导和尾随修剪操作都会停止。例如，如果当前字符串是 `"abc xyz"`，然后 `Trim` 方法返回 `"abc xyz"`。

```cs
// C# program to illustrate the
// method without any parameters
using System;

class GFG {
    // Main Method
    public static void Main()
    {
        string s1 = " GFG";
        string s2 = " GFG ";
        string s3 = "GFG ";

        // Before Trim method call
        Console.WriteLine("Before:");
        Console.WriteLine(s1);
        Console.WriteLine(s2);
        Console.WriteLine(s3);

        Console.WriteLine("");

        // After Trim method call
        Console.WriteLine("After:");
        Console.WriteLine(s1.Trim());
        Console.WriteLine(s2.Trim());
        Console.WriteLine(s3.Trim());
    }
}
```

**输出：**

```cs
Before:
 GFG
 GFG 
GFG

After:
GFG
GFG
GFG
```

### 示例 2

演示 `public string Trim (params char[] trimChars)` 方法的程序。`Trim` 方法从当前字符串中删除参数列表中出现的所有前导和尾随字符。当遇到不在 `trimChars` 中的字符时，每个前导和尾随修剪操作都会停止。例如，当前字符串为 `"123 abc456xyz 789"`，`trimChars` 包含从 `"1"` 到 `"9"` 的数字，则 `Trim` 方法返回 `"ABC 456 yz"`。

```cs
// C# program to illustrate the
// method with parameters
using System;

class GFG {
    // Main Method
    public static void Main()
    {
        // declare char[] array and
        // initialize character 0 to 9
        char[] charsToTrim1 = {'1', '2', '3', '4', '5',
                               '6', '7', '8', '9'};

        string s1 = "123abc456xyz789";
        Console.WriteLine("Before:" + s1);
        Console.WriteLine("After:" + s1.Trim(charsToTrim1));

        Console.WriteLine("");

        char[] charsToTrim2 = { '*', '1', 'c' };
        string s2 = "*123xyz********c******c";
        Console.WriteLine("Before:" + s2);
        Console.WriteLine("After:" + s2.Trim(charsToTrim2));

        Console.WriteLine("");

        char[] charsToTrim3 = { 'G', 'e', 'k', 's' };
        string s3 = "GeeksForGeeks";
        Console.WriteLine("Before:" + s3);
        Console.WriteLine("After:" + s3.Trim(charsToTrim3));

        Console.WriteLine("");

        string s4 = "     Geeks0000";
        Console.WriteLine("Before:" + s4);
        Console.WriteLine("After:" + s4.Trim('0'));
    }
}
```

**输出：**

```cs
Before:123abc456xyz789
After:abc456xyz

Before:*123xyz********c******c
After:23xyz

Before:GeeksForGeeks
After:For

Before:     Geeks0000
After:     Geeks
```

## 关于 Trim() 方法的要点

*   如果修剪方法从当前实例中移除任何字符，此方法不会修改当前实例的值。相反，它返回一个新字符串，其中当前实例的所有前导和尾随空白字符都将被删除。
*   如果当前字符串等于 `null` 或当前实例中的所有字符都由空格字符组成，则此方法返回 `null`。

## 参考

[https://msdn.microsoft.com/en-us/library/system.string.trim](https://msdn.microsoft.com/en-us/library/system.string.trim)