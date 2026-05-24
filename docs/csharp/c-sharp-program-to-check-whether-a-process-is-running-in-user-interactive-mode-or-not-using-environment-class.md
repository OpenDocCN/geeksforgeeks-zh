# 使用环境类检查进程是否在用户交互模式下运行的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-check-a-process-in-user-interactive-mode-or-not-use-environment-class/](https://www.geeksforgeeks.org/c-sharp-program-to-check-whether-a-process-is-running-in-user-interactive-mode-or-not-using-environment-class/)

在 C# 中，环境类提供关于当前平台的信息，并操纵当前平台。它对于获取和设置各种操作系统相关信息非常有用。我们可以这样使用它:它检索命令行参数信息、退出代码信息、环境变量设置信息、调用堆栈信息的内容以及自上次系统启动以来的时间(以毫秒为单位)信息。通过使用一些预定义的方法，我们可以使用环境类获得操作系统的信息。在本文中，我们将讨论如何检查进程是否在用户交互模式下运行。所以我们使用环境类的**用户交互**属性。此属性用于检查进程是否在用户交互模式下运行。如果进程在用户交互模式下运行，它将返回 true。否则，返回 false。

**语法:**

> 环境。用户交互

**返回类型:**该属性的返回类型为布尔值。如果进程以用户交互模式运行，则返回 true 如果进程不以用户交互模式运行，则返回 false

**例:**

## c#

```cs
// C# program to determine whether a process is
// running in user interactive mode or not
// Using Environment class
using System;

class GFG{

static public void Main()
{

    // Declare a variable
    bool result;

    // Checking the process is running in user
    // interactive mode or not
    // Using the UserInteractive property
    result = Environment.UserInteractive;

    // Displaying the result
    if (result == true)
        Console.WriteLine("Yes! the process is running " +
                          "in user interactive mode");
    else
        Console.WriteLine("No! the process is not running " +
                          "in user interactive mode");
}
}
```

**输出:**

```cs
Yes! the process is running in user interactive mode
```