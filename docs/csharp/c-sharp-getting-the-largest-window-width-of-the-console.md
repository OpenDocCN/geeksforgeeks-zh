# C# |获取控制台最大窗口宽度

> 原文:[https://www . geeksforgeeks . org/c-sharp-获得最大的控制台窗口宽度/](https://www.geeksforgeeks.org/c-sharp-getting-the-largest-window-width-of-the-console/)

给定 C# 中的正常控制台，任务是找到控制台的最大可能窗口宽度。

**方法:**这可以使用 C# 中系统包的**控制台**类中的**大窗口**属性来完成。此属性根据当前字体和屏幕分辨率获取最大可能数量的控制台窗口列。

**程序:**寻找最大窗宽

```cs
// C# program to illustrate the
// Console.LargestWindowWidth Property
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace GFG {

class Program {

    static void Main(string[] args)
    {

        // Display Largest Window Width
        Console.WriteLine("Largest Window Width: {0}",
                          Console.LargestWindowWidth);
    }
}
}
```

**输出:**

![](img/6e317425e6796fecb10da0b3c135276b.png)