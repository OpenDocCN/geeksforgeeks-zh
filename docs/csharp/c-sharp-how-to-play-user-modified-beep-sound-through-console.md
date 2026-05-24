# C# |如何通过控制台

播放用户修改的哔哔声

> 原文:[https://www . geesforgeks . org/c-sharp-播放方式-用户修改-哔哔声-通过控制台/](https://www.geeksforgeeks.org/c-sharp-how-to-play-user-modified-beep-sound-through-console/)

给定一个普通的 C# 控制台，任务是通过控制台播放用户修改的哔哔声。用户修改的蜂鸣声是指在特定时间内以特定频率播放的蜂鸣声。

**方法:**这可以借助 C# 的**系统**包中**控制台**类的**哔声(Int32，Int32)** 方法来实现。

**控制台类**的**哔声(int，int)** 方法用于通过控制台扬声器以指定频率在指定持续时间内播放哔声。这些频率和持续时间被指定为该方法的参数。默认情况下，蜂鸣音以 800 赫兹的频率播放，持续时间为 200 毫秒。

> **语法:**公共静态 void Beep (int 频率，int 时长)；
> 
> **参数:**该方法接受两个参数**频率**和**持续时间**，分别是哔哔声必须播放的频率和持续时间。

**异常:**该方法抛出以下异常:

*   **argumentoutofrangerexception**如果频率小于 37 赫兹或者持续时间小于等于零则大于 32767 赫兹。
*   **HostProtectionException** 如果此方法在不允许访问用户界面的服务器(如 SQL Server)上执行。

下面的程序展示了控制台的使用。哔哔声(Int32，Int32)方法:

**程序 1:**

```cs
// C# program to illustrate the use
// of Console.Beep(Int32, Int32) Method
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

        // Set the Frequency
        int frequency = 800;

        // Set the Duration
        int duration = 200;

        // Play beep sound once
        Console.Beep(frequency, duration);
    }
}
}
```

**程序 2:**

```cs
// C# program to illustrate the use
// of Console.Beep(Int32, Int32) Method
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading;
using System.Threading.Tasks;

namespace GFG {

class Program {

    // Main Method
    static void Main(string[] args)
    {

        int n = 5;

        // Set the Frequency
        int frequency = 1000;

        // Set the Duration
        int duration = 400;

        // Play beep sound n times
        for (int i = 1; i < n; i++)
            Console.Beep(frequency, duration);
    }
}
}
```

**注意:**请在离线 Visual Studio 上运行程序，体验输出。