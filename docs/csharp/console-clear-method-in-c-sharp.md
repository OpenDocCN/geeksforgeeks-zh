# 控制台。C# 中的清除方法

> 原文:[https://www . geesforgeks . org/console-clear-method-in-c-sharp/](https://www.geeksforgeeks.org/console-clear-method-in-c-sharp/)

此方法用于清除控制台缓冲区和相应控制台窗口的显示信息。

> **语法:**公共静态 void Clear()；
> 
> **异常:**如果出现输入/输出错误，该方法抛出**异常**。

下面的程序展示了控制台的使用。Clear()方法:

**程序 1:** 显示使用清除方法前的内容

```cs
// C# program to illustrate the use
// of Console.Clear Method 
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

        // Print the statements
        Console.WriteLine("GeeksForGeeks");
        Console.WriteLine("A Computer Science Portal");
        Console.WriteLine("For Geeks");
    }
}
}
```

**Output:**

```cs
GeeksForGeeks
A Computer Science Portal
For Geeks

```

**程序 2:** 使用 clear()方法清除控制台

```cs
// C# program to illustrate the use
// of Console.Clear Method 
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
        // Print the statements
        Console.WriteLine("GeeksForGeeks");
        Console.WriteLine("A Computer Science Portal");
        Console.WriteLine("For Geeks");

        // Clear the Console
        Console.Clear();
    }
}
}
```

**Output:**