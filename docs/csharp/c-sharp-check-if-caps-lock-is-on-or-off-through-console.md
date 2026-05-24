# C# |通过控制台

检查大写锁定是打开还是关闭

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-caps-lock-on-or-off-through-console/](https://www.geeksforgeeks.org/c-sharp-check-if-caps-lock-is-on-or-off-through-console/)

给定 C# 中的正常控制台，任务是通过控制台检查 CAPS LOCK 是打开还是关闭。

**方法:**这可以使用 C# 中系统包的**控制台**类中的 **CAPS LOCK** 属性来完成。

**程序 1:** 当大写锁定开启时

```cs
// C# program to illustrate the
// Console.CapsLock Property
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace GFG {

class Program {

    static void Main(string[] args)
    {

        // Check if CAPS LOCK is on or off
        Console.WriteLine("Is CAPS LOCK on: {0}",
                               Console.CapsLock);
    }
}
}
```

**输出:**

![](img/d48070f0814cb892d3e313e53783d3e4.png)

**程序 2:** 当大写锁定关闭时

```cs
// C# program to illustrate the
// Console.CapsLock Property
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace GFG {

class Program {

    static void Main(string[] args)
    {

        // Check if CAPS LOCK is on or off
        Console.WriteLine("Is CAPS LOCK on: {0}",
                               Console.CapsLock);
    }
}
}
```

**输出:**

![](img/cba362f171451f3abf46c3baff92c423.png)