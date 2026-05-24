# 如何用 C# 中的字符串替换字符？

> 原文:[https://www . geesforgeks . org/如何用 c-sharp 中的字符串替换字符/](https://www.geeksforgeeks.org/how-to-replace-a-character-with-the-string-in-c-sharp/)

给定一个字符串，现在我们的任务是用该字符串替换指定的字符。该任务借助 [Replace()](https://www.geeksforgeeks.org/c-sharp-replace-method/) 方法执行。此方法用于用指定的字符串替换所有 Unicode 字符，并返回修改后的字符串。

**语法:**

> 字符串。替换(字符，新字符串)

这里*字符串*是输入字符串，*T3】一个*字符*出现在要替换的字符串中，new_string 是替换该字符的字符串。*

**示例:**

```cs
Input: A portal in India
Replace A with Hello
Output: Hello portal in India

Input: Python is not equal to java
Replace is with was
Output: Python was not equal to java
```

**进场:**

要用指定的字符串替换字符，请执行以下步骤:

*   Declaration string
*   Use the replace () function to replace the character (that is, "a") with a string (that is, "geek represents geek").

```cs
input_string.Replace("A", "Geeks For Geeks")
```

*   Displays the modified string.

**例:**

## c#

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

**输出:**

```cs
Actual String : A portal in India
Replaced String: Geeks For Geeks portal in India
```