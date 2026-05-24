# C# |检查控制台是否重定向错误

> 原文:[https://www . geeksforgeeks . org/c-sharp-在控制台上检查错误是否被重定向/](https://www.geeksforgeeks.org/c-sharp-check-if-error-is-redirected-on-the-console-or-not/)

给定 C# 中的正常控制台，任务是检查错误是否在控制台上被重定向。

**方法:**这可以使用 C# 中系统包的**控制台**类中的**iserreredirected**属性来完成。此属性返回一个布尔值，说明错误是否被重定向。

**程序:**

```cs
// C# program to illustrate the
// Console.IsErrorRedirected Property
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace GFG {

class Program {

    // Main Method
    static void Main(string[] args)
    {

        // Check if Error is Redirected
        Console.WriteLine("Is Error Redirected: {0}",
                          Console.IsErrorRedirected);
    }
}
}
```

**输出:**

![](img/e8d7c68715970b612eccaceb6e1a3d43.png)