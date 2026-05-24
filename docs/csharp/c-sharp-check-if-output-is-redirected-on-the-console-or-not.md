# C# |检查控制台上的输出是否重定向

> 原文:[https://www . geesforgeks . org/c-sharp-检查输出是否在控制台上重定向/](https://www.geeksforgeeks.org/c-sharp-check-if-output-is-redirected-on-the-console-or-not/)

给定 C# 中的正常控制台，任务是检查输出是否在控制台上被重定向。

**方法:**这可以使用 C# 中系统包的**控制台**类中的**等输出定向**属性来完成。此属性返回一个布尔值，说明输出是否被重定向。

**程序:**

```cs
// C# program to demonstrate the
// Console.IsOutputRedirected Property
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

        // Check if Output is Redirected
        Console.WriteLine("Is Output Redirected: {0}",
                          Console.IsOutputRedirected);
    }
}
}
```

**输出:**

![](img/c31cd04f02e42b5e3ddafd9f8004cdef.png)