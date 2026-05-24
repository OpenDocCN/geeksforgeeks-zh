# C# |如何更改控制台的 buffer width

> 原文:[https://www . geeksforgeeks . org/c-sharp-how-change-bufferwidth-of-the-console/](https://www.geeksforgeeks.org/c-sharp-how-to-change-bufferwidth-of-the-console/)

给定 C# 中的正常控制台，任务是找到缓冲区宽度的默认值，并将其更改为其他值。

***缓冲区宽度*** 是指控制台缓冲区的当前宽度，以列为单位。

**方法:**这可以使用 C# 中系统包的**控制台**类中的**缓冲区宽度**属性来完成。

**程序 1:** 查找默认缓冲区宽度

```cs
// C# program to demonstrate the 
// Console.BufferWidth Property
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

        // Display current Buffer Width
        Console.WriteLine("Default Buffer Width: {0}",
                                Console.BufferWidth);
    }
}
}
```

**输出:**

![](img/dd27f5105980d372ecf6e45d5631bd85.png)

**程序 2:** 将缓冲区宽度更改为 100

```cs
// C# program to demonstrate the 
// Console.BufferWidth Property
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace GFG {

class Program {

    static void Main(string[] args)
    {

        // Display current Buffer Width
        Console.WriteLine("Default Buffer Width: {0}",
                                 Console.BufferWidth);

        // Set the Buffer Width to 100
        Console.BufferWidth = 100;

        // Display current Buffer Width
        Console.WriteLine("Changed Buffer Width: {0}",
                                 Console.BufferWidth);
    }
}
}
```

**输出:**

![](img/c60d08e45bb5fa52be0b1026abaad103.png)

**注意:**查看两个图像中底部水平滚动条的变化情况。