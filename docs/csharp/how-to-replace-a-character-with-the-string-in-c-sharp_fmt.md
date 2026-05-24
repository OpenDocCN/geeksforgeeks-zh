# 如何用 C# 中的字符串替换字符？

> 原文：[https://www.geeksforgeeks.org/how-to-replace-a-character-with-the-string-in-c-sharp/](https://www.geeksforgeeks.org/how-to-replace-a-character-with-the-string-in-c-sharp/)

给定一个字符串，现在我们的任务是用该字符串替换指定的字符。该任务借助 [`Replace()`](https://www.geeksforgeeks.org/c-sharp-replace-method/) 方法执行。此方法用于用指定的字符串替换所有 Unicode 字符，并返回修改后的字符串。

**语法：**

> `string.Replace(char, new_string)`

这里 `string` 是输入字符串，`char` 是出现在字符串中要替换的字符，`new_string` 是替换该字符的字符串。

**示例：**

```cs
Input: A portal in India
Replace A with Hello
Output: Hello portal in India

Input: Python is not equal to java
Replace is with was
Output: Python was not equal to java
```

**思路：**

要用指定的字符串替换字符，请执行以下步骤：

*   声明字符串。
*   使用 `replace()` 函数将字符（例如 `"A"`）替换为字符串（例如 `"Geeks For Geeks"`）。

```cs
input_string.Replace("A", "Geeks For Geeks")
```

*   显示修改后的字符串。

**示例：**

## C\#

```cs
// C# program to replace a character
// with a specified string
using System;

class GFG{

public static void Main()
{

// Define string
    String input_string = "A portal in India";

Console.WriteLine("Actual String : " + input_string);

// Replace the string 'A' with 'Geeks For Geeks'
    Console.WriteLine("Replaced String: " +
         input_string.Replace("A", "Geeks For Geeks"));
}
}
```

**输出：**

```cs
Actual String : A portal in India
Replaced String: Geeks For Geeks portal in India
```