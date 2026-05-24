# C# |如何通过控制台

播放哔哔声

> 原文:[https://www . geesforgeks . org/c-sharp-how-play-beep-sound-through-console/](https://www.geeksforgeeks.org/c-sharp-how-to-play-beep-sound-through-console/)

给定一个普通的 C# 控制台，任务是通过控制台播放哔哔声。

**方法:**这可以借助 C# 的**系统**包中**控制台**类的**哔()**方法来实现。

**控制台类**的**哔()**方法用于通过控制台扬声器播放哔声。

> **语法:**公共静态 void Beep()；
> 
> **异常:**如果此方法在不允许访问用户界面的服务器(如 SQL Server)上执行，此方法将引发 **HostProtectionException** 。

以下程序显示了*控制台的使用。哔()*方法:

**程序 1:**

```cs
// C# program to illustrate the
// Console.Beep Method
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading;
using System.Threading.Tasks;

namespace GFG {

class Program {

    static void Main(string[] args)
    {
        // Play beep sound once
        Console.Beep();
    }
}
}
```

**程序 2:** 播放哔哔声 n 次。

```cs
// C# program to illustrate the
// Console.Beep Method
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading;
using System.Threading.Tasks;

namespace GFG {

class Program {

    static void Main(string[] args)
    {
        int n = 5;

        // Play beep sound n times
        for (int i = 1; i < n; i++)
            Console.Beep();
    }
}
}
```

**注意:**请在离线 Visual Studio 上运行程序，体验输出。