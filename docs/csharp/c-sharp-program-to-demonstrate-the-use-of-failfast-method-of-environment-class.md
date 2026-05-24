# 演示环境类 FailFast()方法使用的 C# 程序

> 原文:[https://www . geeksforgeeks . org/c-sharp-program-to-explain-of-fail fast-of-environment-method-class/](https://www.geeksforgeeks.org/c-sharp-program-to-demonstrate-the-use-of-failfast-method-of-environment-class/)

环境类提供关于当前平台的信息，并操纵当前平台。它对于获取和设置各种操作系统相关信息非常有用。我们可以这样使用它:检索命令行参数信息、退出代码信息、环境变量设置信息、调用堆栈信息的内容以及自上次系统引导以来的时间(以毫秒为单位)信息。在本文中，我们将讨论环境类的 FailFast()方法。该方法可以通过两种不同的方式重载:

**1。FailFast(字符串 msg):** 此方法用于在写入 Windows 应用程序事件日志后立即终止进程，并将错误报告中的消息添加到 Microsoft。它在不运行终结器或 try/catch 块的情况下终止进程。

**语法:**

> 公共静态无效故障快速(字符串消息)

这里， *msg* 是将被记录在 windows 应用程序事件日志中的消息，或者它解释了终止发生的原因。当没有给出解释时，它可以为空。

**2。FailFast(字符串 msg，Exception):** 此方法用于在写入 Windows 应用程序事件日志后立即终止进程，并将错误报告中的消息和异常添加到 Microsoft。在这里，异常不处理，因为进程被终止，但可以获得由于哪个异常发生的信息。在此方法中，当异常为空时，故障快速(字符串消息，异常)方法的行为类似于故障快速(字符串消息)方法。它还在不运行终结器或 try/catch 块的情况下终止进程。

**语法:**

> 公共静态无效故障快速(字符串消息，异常)

这里， *msg* 是一条将被记录在 windows 应用程序事件日志中的消息，或者它解释了为什么会发生终止，以及异常是一个导致终止发生的错误。

让我们借助例子讨论上述概念:

**例 1:**

## C#

```cs
// C# program to illustrate how to use FailFast() method 
// of Environment Class
using System;

class GFG{

static public void Main()
{

    // Code before termination
    Console.WriteLine("Before termination");

    // Usage of FailFast() method to
    // terminate the code
    Environment.FailFast("Stop the program");

    // Code after termination
    Console.WriteLine("After termination");
}
}
```

**输出:**

```cs
Before termination
CLR: Managed code called FailFast, saying "Stop the program"

=================================================================
    Native Crash Reporting
=================================================================
Got a SIGABRT while executing native code. This usually indicates
a fatal error in the mono runtime or one of the native libraries 
used by your application.
=================================================================
```

**例 2:**

在这个例子中，我们在终止前后执行算术运算。

## C#

```cs
// C# program to illustrate how to use FailFast() method 
// of Environment Class
using System;

class GFG{

static public void Main()
{

    // Add two numbers
    int Sum = 10 + 20;
    Console.WriteLine("Sum:" + Sum);

    // Code before termination
    Console.WriteLine("Before termination");

    // Here, we use of FailFast() method to
    // terminate the code
    Environment.FailFast("Stop the program");

    // Code after termination
    Console.WriteLine("After termination");

    // Subtract two numbers
    int Subt = 20-10;
    Console.WriteLine("Subtraction: " + Subt);
}
}
```

**输出:**

```cs
Sum:30
Before termination
CLR: Managed code called FailFast, saying "Stop the program"

=================================================================
    Native Crash Reporting
=================================================================
Got a SIGABRT while executing native code. This usually indicates
a fatal error in the mono runtime or one of the native libraries 
used by your application.
=================================================================
```