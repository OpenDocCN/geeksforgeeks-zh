# 切换 C# 8.0 中的表达式

> 原文:[https://www . geesforgeks . org/switch-expression-in-c-sharp-8-0/](https://www.geeksforgeeks.org/switch-expression-in-c-sharp-8-0/)

switch 语句是一个多路分支语句。它提供了一种简单的方法，可以根据表达式的值将执行转发到代码的不同部分。因此，对于 switch 语句，您总是使用一些重复的 case 和 break 关键字，并且还使用默认语句，如下例所示:

**示例:**

```cs
// C# program to illustrate
// switch case statement
using System;

public class GFG {

    // Main Method
    public static void Main(String[] args)
    {
        int gitem = 8;

        switch (gitem) {

        case 2:
            Console.WriteLine("Hello");
            break;

        case 4:
            Console.WriteLine("Bonjour");

            break;
        case 6:
            Console.WriteLine("Konnichiwa");
            break;

        case 8:
            Console.WriteLine("Namaste");
            break;

        case 10:
            Console.WriteLine("Anyoung haseyo");
            break;

        default:
            Console.WriteLine("No greeting found");
            break;
        }
    }
}
```

**输出:**

```cs
Namaste

```

这是 switch 语句的基本介绍。现在进入主题，我们知道微软已经发布了 C# 的最新版本，也就是 C# 8.0。在 C# 8.0 中，开发人员对 switch 语句做了一些改进，改进后 switch 语句转换成 switch 表达式，改进如下:

*   switch 表达式中使用的变量现在位于 switch 关键字之前。
*   冒号(:)和 case 关键字被替换为箭头(= >)。这使得代码更加紧凑和可读。
*   默认情况现在被替换为丢弃(_)。
*   开关的主体是表达，而不是陈述。

现在，我们根据新的改进修改上面的例子。与传统方法相比，这些新的改进使我们的程序更加紧凑和易于阅读。

**例 1:**

```cs
// C# program to illustrate
// switch expression
using System;

public class GFG {

    // Main Method
    public static void Main(String[] args)
    {
        var gitem = 4;

        var res = gitem switch {
            2 => "Hello",
            4 => "Bonjour",
            6 => "Namaste",
            8 => "Anyoung haseyo",
            _ => "No greeting found",

        };

        Console.WriteLine(res);
    }
}
```

**输出:**

```cs
Bonjour
```

**例 2:**

```cs
// C# program to illustrate 
// how to use string in
// switch expression
using System;

public class GFG {

    // Main Method
    public static void Main(String[] args)
    {
        var sitem = "Second";

        var res = sitem switch {
            "First" => "C#",
            "Second" => "Java",
            "Third" => "C++",
            "Fourth" => "Python",
            _ => "Not Language found !",

        };

        Console.WriteLine("Favorite Language: {0} ", res);
    }
}
```

**输出:**

```cs
Favorite Language: Java 
```