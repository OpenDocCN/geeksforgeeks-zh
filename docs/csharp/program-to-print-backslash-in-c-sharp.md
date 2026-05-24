# 用 C# 打印反斜杠()的程序

> 原文:[https://www . geesforgeks . org/program-to-print-反斜杠 in-c-sharp/](https://www.geeksforgeeks.org/program-to-print-backslash-in-c-sharp/)

**\** 是 C# 中的特殊字符(符号)。它用于转义序列(转义)，例如打印新行-我们使用\n，打印制表符-我们使用 **\t** 。我们必须使用双反斜杠 **(\\)** 来打印反斜杠 **(\)** 。

如果我们在消息中写入，它会抛出一个错误**“无法识别的转义序列”**。

**例:**

```cs
Input  : \\
         Geeksfor\\Geeks
Output : \
         Geeksfor\Geeks

Input : Clean\\Environment
Output: Clean\Environment
```

下面是上述方法的实现:

**例 1:**

## C#

```cs
// C# program to print backslash (\)
using System;
using System.IO;
using System.Text;

namespace geeks {

class GFG {

    // Main Method
    static void Main(string[] args)
    {
        // to print "\"
        Console.WriteLine("\\");

        // to print "\" between string
        Console.WriteLine("Geeksfor\\Geeks");
    }
}
}
```

**输出:**

```cs
\
Geeksfor\Geeks
```

**例 2:**

## c#

```cs
// C# program to print backslash (\)
using System;
using System.Text;

namespace geeks {

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // to print "\" between string
        Console.WriteLine("Green\Clean");
    }
}
}
```

**错误:**

```cs
Unrecognized escape sequence `\C'
```

**例 3:**

## c#

```cs
// C# program to print backslash (\)
using System;
using System.Text;

namespace geeks {

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // to print "\" between string
        Console.WriteLine("Clean\\Environment");

        // to print "\"n and "\"t
        Console.WriteLine("\\n\\t");
    }
}
}
```

**输出:**

```cs
Clean\Environment
\n\t
```