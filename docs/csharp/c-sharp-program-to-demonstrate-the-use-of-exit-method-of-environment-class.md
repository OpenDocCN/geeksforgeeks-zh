# 演示环境类 Exit()方法使用的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-程序演示-使用退出环境方法-类/](https://www.geeksforgeeks.org/c-sharp-program-to-demonstrate-the-use-of-exit-method-of-environment-class/)

环境类提供关于当前平台的信息，并操纵当前平台。环境类对于获取和设置各种操作系统相关信息非常有用。我们可以这样使用它:检索命令行参数信息、退出代码信息、环境变量设置信息、调用堆栈信息的内容以及自上次系统启动以来的时间(以毫秒为单位)信息。通过使用一些预定义的方法，我们可以使用 Environment 类获得操作系统的信息，Exit()方法就是其中之一。它用于终止程序的当前进程，并将退出代码返回给操作系统。调用 Exit()方法在以下方面与 return 语句不同:

*   此方法总是终止应用程序，而 return 语句只有在入口点使用时才能终止应用程序。主方法中的应用程序。
*   即使其他线程正在运行，此方法也会立即终止代码。而 return 语句是在应用程序的入口点调用的，只有当所有前台线程都终止时才会终止应用程序。
*   此方法要求调用方具有调用非托管代码的权限。而 return 语句没有。
*   当从 try 或 catch 块调用此方法时，任何 finally 块中的代码都不会执行。虽然使用了从 try 或 catch 块调用的 return 语句，但 finally 块中的代码确实会执行。
*   如果在受约束的执行区域(CER)中运行代码时调用 Exit 方法，则 CER 不会完全执行。虽然使用了 return 语句，但是 CER 完全执行了。

**语法:**

> 环境。exit(int ExitCode)；

其中 exitCode 是整数类型的参数。它表示将返回操作系统的退出代码。当该参数的值为零时，则意味着该过程完成。当这个参数的值不为零时，这意味着这个过程没有成功完成，或者我们可以说零值代表错误。

**异常:**检测到安全错误时只会抛出*安全异常*。

**例 1:**

## C#

```cs
// C# program to illustrate Exit() method 
// of Environment class
using System;

class GFG{

static public void Main()
{
    Console.WriteLine("Code before Exit() function");

    // Exit the program
    // Using Exit() method
    Environment.Exit(0);

    Console.WriteLine("Code after Exit() function");
}
}
```

**输出**:

```cs
Code before Exit() function
```

**例 2:**

## C#

```cs
// C# program to illustrate Exit() method 
// of Environment class
using System;

class GFG{

static public void Main()
{
    Console.WriteLine("Code Before Exit() function will work");

    // Perform addition
    int add = 9 + 11;
    Console.WriteLine("Sum: " + add);

    // Perform subtraction
    int subtr = 9 - 11;
    Console.WriteLine("Subtract: " + subtr);

    // Exit the program
    Environment.Exit(0);
    Console.WriteLine("Code Before Exit() function will not work");

    // Perform multiplication
    int mult = 9 * 11;
    Console.WriteLine("Multiplication: " + mult);

    // Perform division
    int divide = 10/5;
    Console.WriteLine("Divide: " + divide);
}
}
```

**输出:**

```cs
Code Before Exit() function will work
Sum: 20
Subtract: -2
```