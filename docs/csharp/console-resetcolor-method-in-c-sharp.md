# 控制台。C# 中的 ResetColor()方法

> 原文:[https://www . geesforgeks . org/console-reset color-method-in-c-sharp/](https://www.geeksforgeeks.org/console-resetcolor-method-in-c-sharp/)

**控制台。ResetColor()方法**用于将控制台的前景和背景颜色设置为默认值，即背景为黑色，前景为白色。
**语法:**

```cs
public static void ResetColor ();
```

**例外:**

*   **安全异常**:如果用户没有权限执行动作。
*   **io 异常**:如果出现输入输出错误。

以下程序说明了上述方法的使用:
**示例 1:** 将控制台颜色设置为红色和黄色

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to set the colors to red and yellow
// to demonstrate ResetColor() in next example
using System;

namespace GFG {

class Program {

    // Main Method
    static void Main(string[] args)
    {
        // using BackgroundColor property
        Console.BackgroundColor = ConsoleColor.Yellow;

        // using ForegroundColor property
        Console.ForegroundColor = ConsoleColor.Red;

        Console.WriteLine("Welcome to GeeksForGeeks");
    }
}
}
```

**输出:**

![](img/821cac3d67909acd7327de65792facf3.png)

**示例 2:** 将颜色重置为默认值

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the
// Console.ResetColor Property
using System;
namespace GFG {

class Program {

    // Main Method
    static void Main(string[] args)
    {

        // using ResetColor() Method
        Console.ResetColor();

        Console.WriteLine("Welcome to GeeksForGeeks");
    }
}
}
```

**输出:**

![](img/2beeb3103271dceac9c55bfac599b81f.png)

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . console . reset color？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.console.resetcolor?view=netframework-4.7.2)