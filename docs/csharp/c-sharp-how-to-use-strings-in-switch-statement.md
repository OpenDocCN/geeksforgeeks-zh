# C# |如何在 switch 语句中使用字符串

> 原文:[https://www . geesforgeks . org/c-sharp-switch-statement 中的字符串使用方法/](https://www.geeksforgeeks.org/c-sharp-how-to-use-strings-in-switch-statement/)

**[开关语句](https://www.geeksforgeeks.org/c-sharp-decision-making-else-else-ladder-nested-switch-nested-switch/# switch)** 是多路分支语句。它提供了一种简单的方法，可以根据表达式的值将执行转发到代码的不同部分。*字符串是开关语句中唯一可以使用的非整数类型*。

**重要点:**

*   就执行而言，打开字符串可能比打开 **[原始数据类型](https://www.geeksforgeeks.org/c-data-types-2/)** 更昂贵。因此，最好只在控制数据已经是字符串形式的情况下才打开字符串。
*   switch 语句中字符串对象之间的比较区分大小写。
*   在 switch case 中必须使用 break 语句。

**例 1:**

```cs
// C# program to illustrate hwo to use
// a string in switch statement
using System;

class GFG {

    // Main Method
    static public void Main()
    {
        string str = "one";

        // passing string "str" in 
        // switch statement
        switch (str) {

        case "one":
            Console.WriteLine("It is 1");
            break;

        case "two":
            Console.WriteLine("It is 2");
            break;

        default:
            Console.WriteLine("Nothing");
            break;
        }
    }
}
```

**输出:**

```cs
It is 1
```

**例 2:**

```cs
// C# program to illustrate hwo to use
// a string in switch statement
using System;

class GFG {

    // Main Method
    static public void Main()
    {
        string subject = "C#";

        // passing string "subject" in 
        // switch statement
        switch (subject) {

        case "Java":
            Console.WriteLine("Subject is Java");
            break;

        case "C++":
            Console.WriteLine("Subject is C++");
            break;

        default:
            Console.WriteLine("Subject is C#");
            break;
        }
    }
}
```

**输出:**

```cs
Subject is C#

```