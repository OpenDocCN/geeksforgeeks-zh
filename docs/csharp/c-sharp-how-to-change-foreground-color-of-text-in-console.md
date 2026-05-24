# C# |如何在控制台

更改文本前景色

> 原文:[https://www . geesforgeks . org/c-sharp-如何更改-控制台中文本的前景色/](https://www.geeksforgeeks.org/c-sharp-how-to-change-foreground-color-of-text-in-console/)

给定 C# 中的普通控制台，文本前景的默认颜色是“黑色”。任务是将这种颜色改为其他颜色。

**方法:**这可以使用 C# 中系统包的**控制台**类中的**前景颜色**属性来完成。

**程序 1:** 将控制台前景色更改为蓝色。

```cs
// C# program to illustrate the 
// ForegroundColor property
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace GFG {

class Program {

    static void Main(string[] args)
    {

        // Display current Foreground color
        Console.WriteLine("Default Foreground Color: {0}",
                                 Console.ForegroundColor);

        // Set the Foreground color to blue
        Console.ForegroundColor
            = ConsoleColor.Blue;

        // Display current Foreground color
        Console.WriteLine("Changed Foreground Color: {0}",
                                Console.ForegroundColor);
    }
}
}
```

**输出:**

![](img/dda24cdb2317de17fb3246fb1b00e2da.png)

**程序 2:** 可以改变前景颜色的可用颜色列表如下

```cs
// C# program to get the
// list of available colors
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace GFG {

class Program {

    static void Main(string[] args)
    {

        // Get the list of available colors
        // that can be changed
        ConsoleColor[] consoleColors
            = (ConsoleColor[])ConsoleColor
                  .GetValues(typeof(ConsoleColor));

        // Display the list
        // of available console colors
        Console.WriteLine("List of available "
                          + "Console Colors:");
        foreach(var color in consoleColors)
            Console.WriteLine(color);
    }
}
}
```

**输出:**

![](img/88d28f6b679ce2b4df391cd903884262.png)