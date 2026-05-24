# C# |如何更改控制台左窗

> 原文:[https://www . geeksforgeeks . org/c-sharp-如何更改控制台左侧的窗口/](https://www.geeksforgeeks.org/c-sharp-how-to-change-the-windowleft-of-the-console/)

给定 C# 中的普通控制台，任务是更改控制台的左窗口。

**方法:**这可以使用 C# 中系统包的**控制台**类中的**窗口左**属性来完成。**窗口左侧**获取或设置控制台窗口区域相对于屏幕缓冲区的最左侧位置。

**程序 1:** 获取 WindowLeft 的值

```cs
// C# program to illustrate the
// Console.WindowLeft Property
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace GFG {

class Program {

    static void Main(string[] args)
    {

        // Get the WindowLeft
        Console.WriteLine("Current WindowLeft: {0}",
                                Console.WindowLeft);
    }
}
}
```

**输出:**

![](img/f569ca31efd96b56c7e689ad31a3fc3f.png)

**程序 2:** 设置窗口左侧的值

```cs
// C# program to illustrate the
// Console.WindowLeft Property
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace GFG {

class Program {

    static void Main(string[] args)
    {

        // Get the WindowWidth
        Console.WriteLine("Current WindowLeft: {0}",
                                Console.WindowLeft);

        // Set the WindowWidth
        Console.BufferWidth = 100;
        Console.WindowLeft = 10;

        // Get the WindowWidth
        Console.Write("Current WindowLeft: {0}",
                            Console.WindowLeft);
    }
}
}
```

**输出:**

![](img/98eb1e9fe4658ab9088945b2f2d47979.png)

**注意:**在两幅图像中都可以看到窗口底部的水平滚动条。